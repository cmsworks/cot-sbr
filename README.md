cot-sbr
=======

Сделка без риска для фриланс-биржи на Cotonti

Разработчик: Булат Юсупов support@cmsworks.ru

Copyright CMSWorks Team 2016

Плагин позволяет организовать на сайте фриланс-биржи возможность пользователям оформлять между собой сделки с полным согласованием всех этапов работ. При этом бюджет сделки резервируется на счету сайта до начала всех работ и выплачивается Исполнителю после приемки результатов работ по каждому этапу сделки. При возникновении спорных вопросов, любая из сторон может обратиться в арбитражную комиссию (в администрацию сайта). Арбитражная комиссия, путем анализа внутренней переписки по сделке, принимает соответствующее решение об оплате выполненной работы Исполнителю, либо о возврате бюджета за этап сделки Заказчику. Также комиссия может принять решение о частичной выплате сторонам. Таким образом осуществляется защита всех сторон сделки.

###Описание принципа работы:

1. Создание сделки и согласование условий

Оформление сделки начинается с выбора исполнителя. На странице проекта Заказчик выбирает наиболее подходящее предложение и переходит по кнопке "Предложить сделку". В открывшейся форме Заказчик должен заполнить всю необходимую информацию о будущем заказе и указать все этапы сделки. Каждый этап должен содержать заголовок, техническое задание (ТЗ). бюджет и сроки, необходимые для выполнения указанных работ. Общий бюджет сделки суммируется из бюджетов каждого из этапов. Таким образом формируется основной документ безопасной сделки. После того как вся информация заполнена, Заказчик отправляет ее на согласование выбранному Исполнителю. В случае, если Исполнитель не согласен с условиями сделки, то Заказчик может изменить текст и отправить сделку на повторное согласование. Если Исполнитель соглашается со всеми указанными условиями, то об этом уведомляется Заказчик. После этого Заказчик должен оплатить общий бюджет сделки, в том числе с учетом комиссии сервиса. Размер комиссии устанавливается администратором сайта и является платой за проведение на сайте данного вида услуг. 

Как только Заказчик оплатил сделку, Исполнитель может приступать к исполнению первого этапа.

2. Исполнение этапов и завершение сделки

Этап сделки должен быть выполнен в заранее согласованные строки. При этом стороны могут обмениваться сообщениями с помощью системы переписки на странице этапа сделки. Это позволяет уточнять различные вопросы и согласовывать промежуточные результаты выполняемых работ. После того как были выполнены все работы и обязательства по текущему этапу Заказчик принимает работу и тем самым закрывает данные этап сделки. Исполнителю на счет переводится оплата за данный этап. 

Завершение сделки осуществляется автоматически после приемки всех этапов. 

3. Арбитраж

Если в ходе выполнения какого-либо из этапов возникли разногласия между сторонами сделки, можно обратиться в арбитраж для разрешения ситуации. Арбитражная комиссия принимает свое решение путем анализа сложившейся ситуации. Комиссия может принять решение о полной или частичной выплате (возврате) суммы за текущий этап сделки Заказчику или Исполнителю. Решение арбитражной комиссии нельзя отменить.

 
###Сделки без привязки в проектам

Если вы хотите использовать сделки вне проектов, то можно создать ссылку на создание сделки в любом шаблоне сайта таким образом:

\<a href="{PHP|cot_url('sbr', 'm=add')}">Предложить сделку\</a>

Либо, если нужно разместить кнопку на странице пользователя (users.details.tpl), то ссылка будет выглядеть так:

\<a href="{USERS_DETAILS_ID|cot_url('sbr', 'm=add&uid='$this)}">Предложить сделку\</a>
 

###Установка:

Распакуйте и скопируйте папку sbr в директорию plugins/ вашего сайта.
Зайдите в админ-панель сайта и перейдите в раздел "Расширения". Установите плагин Sbr.
В настройках плагина укажите размер комиссии сайта за оформление следки (в процентах) и другие настройки. Комиссия за оформление сделки взимается с Заказчика. Также при необходимости в настройках плагина можно указать размер комиссии с Исполнителя, которая взимается при выплате на счет Исполнителя по мере приемки каждого этапа сделки. Исполнитель получит оплату уже с учетом указанной комиссии.
В шапку сайта можно добавить ссылку на сделки (этот код уже вставлен в базовую версию фриланс-биржи, здесь показан для примера):

<!-- IF {PHP.cot_plugins_active.sbr} -->
      <li><a href="{PHP|cot_url('sbr')}">{PHP.L.sbr_mydeals}</a></li>
<!-- ENDIF -->
 

Прикрепление файлов к этапам сделки и к переписке по сделке

В настройках плагина можно указать директорию для хранения файлов, а также перечень расширений файлов, допустимых к загрузке. По-умолчанию, директория для загрузки файлов: datas/sbr. При установке плагина, создайте данную папку в соответствии с указанной директорией и установите на нее права 777.
Работа с файлами на данный момент создана в режиме тестирования
