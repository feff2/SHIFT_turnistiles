# Небольшое предисловие:"Турникеты" от ЦФТ ШИФТ мое первое ML соревнование, которое многое мне дало. Да, выполнение задания нельзя назвать идеальным, но опыт довольно ценный. Я первый раз столкнулся на практике с такой качественной задачей.
# Что же нужно сделать? Необходимо научить модель понимать, что за пользователь прошел через турникет, но есть один нюанс: в train пользователи представлены user_id, то есть числом, а в test user_word, то есть "словом".  
# Изначально мы имеем следующие данные: время и дату прохождения каждого турникета, id турникета и user_id или user_word(в зависимости train или test это)
# Что сделал я для решения этой задачи? 
# 1. Было принято решение время и дату разбить на отдельные признаки: время(а точнее час) и день недели. Я считаю, что день недели более значимая информация, чем абстрактная дата.
# 2. Кодировка здесь ненужна, так как использовался catboost. Модель сама хорошо разбирается с категориальными переменными
# 3. Необходимо нормализовать время, чтобы не было выбросов 
# Почему catboost? Здесь много категориальных переменных, а catboost хорошо с ними работает + всё-таки это соревнование воспринималось мной как опыт/время для эксперементов, а конкретно с catboost я до этого не работал
# Итог: в Leaderboard я не был на самых высоких местах в leaderboard(73 из 135), но опыт в работе с данными и catboost я получил хороший, также важно то, что у меня сложилось понимание следующей идеи: "Не все твои мысли приведут к улучшению результата". Например: добавление признака выходной день это или нет вообще никак не повлиял на результат  
# Безусловно этот проект можно улучшить, например: добавить последовательность и разницу во времени между прохождений турников пользователем, посмотреть активность пользователей по месяцам и сделать разбиение в зависимости от этого. Эти мысли пришли мне уже поздно и, к сожалению, я не успел реализовать их во время соревнования, потому реализации этих идей нет в ноутбуке.
