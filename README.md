# templates-base.html<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <title>{% block title %}MEXC Trading Bot{% endblock %}</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body { margin: 0; font-family: 'Segoe UI', Arial, sans-serif; background: #f9f9f9;}
        nav { display: flex; justify-content: space-around; background: #222; color: #fff; position: fixed; bottom: 0; left: 0; width: 100%; height: 60px; align-items: center; box-shadow: 0 -2px 5px #ccc; }
        nav a { color: #fff; text-decoration: none; text-align: center; font-size: 1.1em; flex: 1; padding: 8px 0; }
        nav a.active { color: #4caf50; font-weight: bold; }
        .container { padding: 20px 10px 80px 10px; max-width: 600px; margin: 0 auto;}
        h1 { font-size: 1.7em; margin-top: 10px;}
        @media (max-width: 600px) {
            .container { padding-top: 15px; }
            nav { height: 50px; font-size: 0.95em;}
        }
    </style>
</head>
<body>
    <div class="container">
        {% block content %}{% endblock %}
    </div>
    <nav>
        <a href="/" {% if request.path=='/' %}class="active"{% endif %}>🏠</a>
        <a href="/analysis" {% if request.path=='/analysis' %}class="active"{% endif %}>📊</a>
        <a href="/history" {% if request.path=='/history' %}class="active"{% endif %}>🕓</a>
        <a href="/portfolio" {% if request.path=='/portfolio' %}class="active"{% endif %}>💼</a>
        <a href="/settings" {% if request.path=='/settings' %}class="active"{% endif %}>⚙️</a>
    </nav>
</body>
</html>
