# Администратор на Django

За добавяне, редактиране и изтриване на публикациите, които току-що моделирахме, ще използваме администратора на Django.

Нека отворим файла `blog/admin.py` в редактора на кода и заменим съдържанието му с това:

{% filename %}blog/admin.py{% endfilename %}

```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```

Както можете да видите, ние импортираме (включваме) модела Post, дефиниран в предишната глава. За да направим модела ни видим на страницата на администратора, трябва да регистрираме модела с `admin.site.register(Post)`.

Добре, време да разгледаме нашия модел Post. Не забравяйте да стартирате `python manage.py runserver` в конзолата, за да стартирате уеб сървъра. Отидете до вашия браузър и напишете адреса http://127.0.0.1:8000/admin/. Ще видите страница за вход като тази:

![Страница за вход](images/login_page2.png)

За да влезете, трябва да създадете *superuser* - потребителски акаунт, който има контрол върху всичко в сайта. Върнете се в командния ред, напишете `python manage.py createsuperuser` и натиснете enter.

> Не забравяйте, че за да пишете нови команди, докато уеб сървърът работи, отворете нов прозорец на терминала и активирайте своя virtualenv. Прегледахме как да пишете нови команди във **Вашия първи проект на Django!**, в секцията **Стартиране на уеб сървъра**.

{% filename %}macOS or Linux:{% endfilename %}

    (myvenv) ~/djangogirls$ python manage.py createsuperuser
    

{% filename %}Windows:{% endfilename %}

    (myvenv) C:\Users\Name\djangogirls> python manage.py createsuperuser
    

Когато бъдете подканени, въведете потребителското си име (малки букви, без интервали), имейл адрес и парола. **Не се притеснявайте, че не можете да видите паролата, която въвеждате - така трябва да бъде.** Въведете я и натиснете `enter`, за да продължите. Резултатът трябва да изглежда така (където потребителското име и имейл трябва да са ваши собствени):

    Username: ola
    Email address: ola@example.com
    Password:
    Password (again):
    Superuser created successfully.
    

Върнете се в браузъра си. Влезте с избраните от вас име и парола на superuser; трябва да видите таблото за управление на Django.

![Django администратор](images/django_admin3.png)

Отидете на постове и експериментирайте малко с тях. Добавете пет или шест публикации в блога. Не се притеснявайте за съдържанието - вижда се само на вашия локален компютър - можете да копирате и поставите някакъв текст от този урок, за да спестите време. :)

Уверете се, че поне две или три публикации (но не всички) имат зададена дата на публикуване. По-късно ще бъде полезно.

![Django администратор](images/edit_post3.png)

Ако искате да знаете повече за администратора на Django, трябва да проверите документацията на Django: https://docs.djangoproject.com/en/2.2/ref/contrib/admin/

Това вероятно е подходящ момент да вземете кафе (или чай) или нещо за хапване, за да се "заредите". Създадохте първия си модел Django - заслужавате малка почивка!