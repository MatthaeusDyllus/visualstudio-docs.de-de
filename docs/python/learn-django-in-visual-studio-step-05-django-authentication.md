---
title: 'Tutorial: Informationen zu Django in Visual Studio – Schritt 5'
description: In dieser exemplarischen Vorgehensweise erhalten Sie grundlegende Informationen zu Django im Zusammenhang mit Visual Studio-Projekten, insbesondere zu Authentifizierungsfeatures, die durch die Vorlage „Django-Webprojekt“ bereitgestellt werden.
ms.date: 04/25/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: tutorial
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: e2c5f9461eafa83551ba15c36d8ef212922a52ff
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="tutorial-step-5-authenticate-users-in-django"></a>Tutorial Schritt 5: Authentifizieren von Benutzern bei Django

**Vorheriger Schritt:[ Verwenden der vollständigen Vorlage „Django-Webprojekt“](learn-django-in-visual-studio-step-04-full-django-project-template.md)**

Da die Authentifizierung eine allgemeine Voraussetzung für Web-Apps ist, enthält die Vorlage „Django-Webprojekt“ einen grundlegenden Authentifizierungsablauf. (Die Vorlage „Fragt ein Django-Webprojekt ab“ aus Schritt 6 dieses Tutorials umfasst auch den gleichen Ablauf.) Bei Verwendung einer der Django-Projektvorlagen enthält Visual Studio die erforderlichen Module für die Authentifizierung der `settings.py` des Django-Projekts.

In diesem Schritt erhalten Sie die folgenden Informationen:

> [!div class="checklist"]
> - Verwenden des Authentifizierungsablaufs in den Visual Studio-Vorlagen (Schritt 5-1)

## <a name="step-5-1-use-the-authentication-flow"></a>Schritt 5-1: Verwenden Sie den Authentifizierungsablauf

Die folgenden Schritte führen den Authentifizierungsablauf aus, und beschreiben die beteiligten Teile des Projekts:

1. Wenn Sie die Anweisungen der `readme.html`-Datei im Projektstammverzeichnis zum Erstellen eines Administratorkontos (Administrator) noch nicht befolgt haben, holen Sie dies jetzt nach.

1. Führen Sie die App aus Visual Studio mit **Debuggen** > **Debuggen starten** (F5) durch. Wenn die App im Browser angezeigt wird, beachten Sie, dass **Anmelden** an der oberen rechten Ecke der Navigationsleiste angezeigt wird.

    ![Steuerelement für die Anmeldung auf der App-Seite „Django-Webprojekt“](media/django/step05-login-control.png)

1. Öffnen Sie `templates/app/layout.html`, und beachten Sie, dass das `<div class="navbar ...>`-Element das `{% include app/loginpartial.html %}`-Tag enthält. Das `{% include %}`-Tag weist das Vorlagensystem von Django an, den Inhalt der enthaltenen Datei an diesem Punkt in der enthaltenen Vorlage zu erhalten.

1. Öffnen Sie `templates/app/loginpartial.html`, und beobachten Sie, wie das bedingte Tag `{% if user.is_authenticated %}` zusammen mit einem `{% else %}`-Tag zum Rendern der verschiedenen UI-Elemente verwendet wird, je nachdem, ob der Benutzer etwas authentifiziert hat:

    ```html
    {% if user.is_authenticated %}
    <form id="logoutForm" action="/logout" method="post" class="navbar-right">
        {% csrf_token %}
        <ul class="nav navbar-nav navbar-right">
            <li><span class="navbar-brand">Hello {{ user.username }}!</span></li>
            <li><a href="javascript:document.getElementById('logoutForm').submit()">Log off</a></li>
        </ul>
    </form>

    {% else %}

    <ul class="nav navbar-nav navbar-right">
        <li><a href="{% url 'login' %}">Log in</a></li>
    </ul>

    {% endif %}
    ```

1. Da kein Benutzer beim ersten Start der App authentifiziert wurde, rendert dieser Vorlagencode nur die Verknüpfung „Anmelden“ zum relativen Pfad „Anmeldung“. Wie in `urls.py` im vorherigen Abschnitt gezeigt, wird diese Route der `django.contrib.auth.views.login`-Ansicht zugeordnet, die die folgenden Daten erhält:

    ```python
    {
        'template_name': 'app/login.html',
        'authentication_form': app.forms.BootstrapAuthenticationForm,
        'extra_context':
        {
            'title': 'Log in',
            'year': datetime.now().year,
        }
    }
    ```

    Hier identifiziert `template_name` die Vorlage für die Anmeldeseite, in diesem Fall `templates/app/login.html`. Die `extra_context`-Eigenschaft wird zu den Standardkontextdaten in der Vorlage hinzugefügt. Schließlich gibt `authentication_form` eine Formularklasse an, die mit der Anmeldung in der Vorlage verwendet wird, in der sie als `form`-Objekt angezeigt wird. Der Standardwert ist `AuthenticationForm` (aus `django.contrib.auth.views`); die Visual Studio-Projektvorlage verwendet stattdessen das in der `forms.py`-Datei der App definierte Formular:

    ```python
    from django import forms
    from django.contrib.auth.forms import AuthenticationForm
    from django.utils.translation import ugettext_lazy as _

    class BootstrapAuthenticationForm(AuthenticationForm):
        """Authentication form which uses boostrap CSS."""
        username = forms.CharField(max_length=254,
                                   widget=forms.TextInput({
                                       'class': 'form-control',
                                       'placeholder': 'User name'}))
        password = forms.CharField(label=_("Password"),
                                   widget=forms.PasswordInput({
                                       'class': 'form-control',
                                       'placeholder':'Password'}))
    ```

    Wie Sie sehen können, wird diese Formularklasse von `AuthenticationForm` abgeleitet und überschreibt insbesondere die Felder „Benutzername“ und „Kennwort“, um Platzhaltertext hinzuzufügen. Die Visual Studio-Vorlage enthält diesen expliziten Code unter der Annahme, dass Sie das Formular wahrscheinlich anpassen möchten, und z.B. eine Überprüfung für die Kennwortsicherheit hinzufügen.

1. Wenn Sie zur Anmeldeseite navigieren, rendert die App die `login.html`-Vorlage. Die Variablen `{{ form.username }}` und `{{ form.password }}` rendern das `CharField`-Formular aus `BootstrapAuthenticationForm`. Es gibt auch einen integrierten Abschnitt, der Validierungsfehler anzeigt, und ein vorgefertigtes Element für Anmeldungen bei sozialen Netzwerken, wenn Sie diese Dienste hinzufügen möchten.

    ```html
    {% extends "app/layout.html" %}

    {% block content %}

    <h2>{{ title }}</h2>
    <div class="row">
        <div class="col-md-8">
            <section id="loginForm">
                <form action="." method="post" class="form-horizontal">
                    {% csrf_token %}
                    <h4>Use a local account to log in.</h4>
                    <hr />
                    <div class="form-group">
                        <label for="id_username" class="col-md-2 control-label">User name</label>
                        <div class="col-md-10">
                            {{ form.username }}
                        </div>
                    </div>
                    <div class="form-group">
                        <label for="id_password" class="col-md-2 control-label">Password</label>
                        <div class="col-md-10">
                            {{ form.password }}
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="col-md-offset-2 col-md-10">
                            <input type="hidden" name="next" value="/" />
                            <input type="submit" value="Log in" class="btn btn-default" />
                        </div>
                    </div>
                    {% if form.errors %}
                    <p class="validation-summary-errors">Please enter a correct user name and password.</p>
                    {% endif %}
                </form>
            </section>
        </div>
        <div class="col-md-4">
            <section id="socialLoginForm"></section>
        </div>
    </div>

    {% endblock %}
    ```

1. Wenn Sie das Formular einreichen, versucht Django, die Anmeldeinformationen, die Sie übermitteln, zu authentifizieren (z.B. die Anmeldeinformationen des Administrators). Wenn die Authentifizierung fehlschlägt, bleiben Sie auf derselben Seite, aber `form.errors` wird auf „TRUE“ festgelegt. Wenn die Authentifizierung erfolgreich ist, navigiert Django zur relativen URL im Feld „Weiter“, `<input type="hidden" name="next" value="/" />`, welches in diesem Fall die Startseite ist (`/`).

1. Wenn die Startseite erneut gerendert wird, ist die `user.is_authenticated`-Eigenschaft „TRUE“, wenn die `loginpartial.html`-Vorlage gerendert wird. Daher sehen Sie die Nachricht „Hallo (Benutzername)“ und „Abmelden“. Sie können `user.is_authenticated` in anderen Teilen der App verwenden, um die Authentifizierung zu überprüfen.

    ![Hallo-Nachricht und Steuerelement für die Abmeldung auf der App-Seite „Django-Webprojekt“](media/django/step05-logoff-control.png)

1. Um zu überprüfen, ob der authentifizierte Benutzer für den Zugriff auf bestimmte Ressourcen autorisiert ist, müssen Sie benutzerspezifische Berechtigungen aus der Datenbank für diesen Benutzer abrufen. Weitere Informationen finden Sie unter [Using the Django authentication system (Verwenden des Authentifizierungssystems von Django)](https://docs.djangoproject.com/en/2.0/topics/auth/default/#permissions-and-authorization) (Django-Dokumentation).

1. Der Administrator ist insbesondere dazu autorisiert, mit den relativen URLs „/admin/“ und „/admin/doc/“ auf die integrierte Django-Administratorschnittstellen zuzugreifen. Um diese Schnittstellen zu aktivieren, öffnen Sie `urls.py` des Django-Projekts, und entfernen Sie die Kommentare aus den folgenden Einträgen:

    ```python
    from django.conf.urls import include
    from django.contrib import admin
    admin.autodiscover()

    # ...
    urlpatterns = [
        # ...
        url(r'^admin/doc/', include('django.contrib.admindocs.urls')),
        url(r'^admin/', include(admin.site.urls)),
    ]
    ```

    Wenn Sie die App neu starten, navigieren Sie zu „/admin/“ und „/admin/doc/“, und führen Sie Aufgaben wie das Erstellen von zusätzlichen Benutzerkonten aus.

    ![Administratorschnittstelle von Django](media/django/step05-administrator-interface.png)

1. Die letzte Phase des Authentifizierungsablaufs ist das Abmelden. Wie Sie in `loginpartial.html` sehen, führt die Verknüpfung **Abmelden** einfach eine POST-Anforderung zur relativen URL „/login“ hinzu, die von der integrierten Ansicht `django.contrib.auth.views.logout` verarbeitet wird. In dieser Ansicht wird keine Benutzeroberfläche angezeigt, Sie werden einfach zur Startseite weitergeleitet (wie in `urls.py` für das „^logout$“-Muster gezeigt). Wenn Sie eine Abmeldeseite anzeigen möchten, ändern Sie zunächst das URL-Muster wie folgt, um die „template_name“-Eigenschaft hinzuzufügen, und die „next_page“-Eigenschaft zu entfernen:

    ```python
    url(r'^logout$',
        django.contrib.auth.views.logout,
        {
            'template_name': 'app/loggedoff.html',
            # 'next_page': '/',
        },
        name='logout')
    ```

    Erstellen Sie dann `templates/app/loggedoff.html` mit folgendem (minimalen) Inhalt:

    ```html
    {% extends "app/layout.html" %}
    {% block content %}
    <h3>You have been logged off</h3>
    {% endblock %}
    ```

    Das Ergebnis erscheint wie folgt:

    ![Hinzugefügte Abmeldeseite](media/django/step05-logged-off-page.png)

1. Wenn Sie fertig sind, beenden Sie den Server, und übertragen Sie Ihre Änderungen erneut zur Quellcodeverwaltung.

### <a name="question-what-is-the-purpose-of-the--crsftoken--tag-that-appears-in-the-form-elements"></a>Frage: Was ist der Zweck des Tags {% srsf_token %}, das in den \<Formular\>-Elementen auftritt?

Antwort: Das `{% crsf_token %}`-Tag enthält den integrierten [Schutz vor der websiteübergreifenden Anforderungsfälschung (CSRF)](https://docs.djangoproject.com/en/2.0/ref/csrf/) von Django (Django-Dokumentation). In der Regel fügen Sie dieses Tag zu einem Element hinzu, das über POST-, PUT- oder DELETE-Anforderungsmethoden verfügt, wie Formulare, und die Vorlagenrenderingfunktion (`render`) fügt den erforderlichen Schutz hinzu.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Use the Polls Django Web Project template (Verwenden der Vorlage „Fragt ein Django-Webprojekt ab“)](learn-django-in-visual-studio-step-06-polls-django-web-project-template.md)

## <a name="going-deeper"></a>Vertiefung

- [User authentication in Django (Benutzerauthentifizierung in Django)](https://docs.djangoproject.com/en/2.0/topics/auth/) (docs.djangoproject.com)
- Quellcode des Tutorials auf GitHub: [Microsoft/python-sample-vs-learning-django](https://github.com/Microsoft/python-sample-vs-learning-django)