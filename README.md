<!DOCTYPE html>
<html lang="ru">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Персональный тренер в Киеве - Данило</title> <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet"> <link href="https://fonts.cdnfonts.com/css/montserrat" rel="stylesheet">
    <style>
        /* Обновленные общие стили в стиле trener.ua */
        body {
            font-family: 'Roboto', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f8f8f8; /* Светло-серый фон как на trener.ua */
            color: #333; /* Темно-серый основной цвет текста */
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 20px auto; /* Уменьшены верхний и нижний отступы */
            padding: 30px;
            background-color: #fff; /* Белый фон контейнера */
            box-shadow: 0 0 15px rgba(0, 0, 0, 0.1); /* Более легкая тень */
            border-radius: 8px; /* Менее скругленные углы контейнера */
        }

        h1, h2 {
            font-family: 'Montserrat', sans-serif; /* Montserrat для заголовков */
            color: #2c3e50; /* Более темный цвет заголовков */
            font-weight: 700;
            margin-top: 20px; /* Уменьшены отступы сверху для заголовков */
            margin-bottom: 15px; /* Уменьшены отступы снизу для заголовков */
        }

        h1 {
            font-size: 2.8em; /* Уменьшен размер H1 */
            text-align: center; /* Центрирование H1 */
        }

        h2 {
            font-size: 2em; /* Уменьшен размер H2 */
        }

        p {
            font-size: 1.1em; /* Уменьшен размер основного текста */
            color: #555; /* Цвет основного текста чуть светлее */
            margin-bottom: 15px; /* Уменьшены отступы снизу для параграфов */
        }

        .stats {
            font-weight: 500; /* Средняя жирность для статистики */
            font-size: 1.2em; /* Уменьшен размер статистики */
            color: #3498db; /* Синий цвет для статистики, как акцент на trener.ua */
            display: block; /* Чтобы каждый показатель был на новой строке */
            margin-bottom: 8px; /* Уменьшенный отступ для статистики */
        }

        .button {
            display: inline-block;
            padding: 12px 25px; /* Уменьшены padding для кнопки */
            background-color: #3498db; /* Синий цвет кнопки, как на trener.ua */
            color: white;
            text-decoration: none;
            border-radius: 5px; /* Менее скругленные углы кнопки */
            font-size: 1.1em; /* Уменьшен размер шрифта кнопки */
            font-weight: 500; /* Средняя жирность шрифта кнопки */
            transition: background-color 0.3s ease;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Легкая тень для кнопки */
        }

        .button:hover {
            background-color: #2980b9; /* Более темный синий при наведении */
        }

        #modal {
            display: none;
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgba(0, 0, 0, 0.4); /* Полупрозрачный фон модалки */
        }

        .modal-content {
            background-color: #fefefe;
            margin: 15% auto; /* Увеличен верхний отступ для модалки */
            padding: 25px; /* Уменьшен padding в модалке */
            border: 1px solid #888;
            width: 80%; /* Ширина модалки */
            border-radius: 8px; /* Скругленные углы модалки */
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px; /* Уменьшен размер крестика */
            font-weight: bold;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        /* Стили для формы в модальном окне */
        .modal-form label {
            display: block;
            margin-top: 10px; /* Уменьшены отступы для label */
            font-weight: bold;
            color: #333; /* Цвет текста label */
        }

        .modal-form input[type="text"],
        .modal-form input[type="email"],
        .modal-form input[type="tel"],
        .modal-form textarea {
            width: 100%;
            padding: 10px; /* Уменьшены padding для полей формы */
            margin-top: 5px; /* Уменьшены отступы сверху для полей */
            border: 1px solid #ddd;
            border-radius: 4px; /* Менее скругленные углы для полей */
            box-sizing: border-box;
            font-size: 1em; /* Уменьшен размер шрифта в полях */
            color: #333; /* Цвет текста в полях */
        }

        .modal-form textarea {
            height: 120px; /* Уменьшена высота textarea */
        }

        .modal-form button {
            background-color: #3498db; /* Синий цвет кнопки формы */
            color: white;
            padding: 10px 20px; /* Уменьшены padding для кнопки формы */
            border: none;
            border-radius: 5px; /* Менее скругленные углы кнопки формы */
            font-size: 1.1em; /* Уменьшен размер шрифта кнопки формы */
            cursor: pointer;
            margin-top: 20px; /* Уменьшены отступы сверху для кнопки формы */
            font-weight: 500; /* Средняя жирность шрифта кнопки формы */
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .container {
                padding: 20px; /* Уменьшены padding для мобильных устройств */
                margin: 10px auto; /* Уменьшены отступы на мобильных */
                border-radius: 6px; /* Менее скругленные углы на мобильных */
            }

            h1 {
                font-size: 2.2em; /* Уменьшен размер заголовка на мобильных */
            }

            h2 {
                font-size: 1.6em; /* Уменьшен размер подзаголовков на мобильных */
            }

            p {
                font-size: 1em; /* Уменьшен размер основного текста на мобильных */
            }

            .button {
                font-size: 1em; /* Уменьшен размер кнопки на мобильных */
                padding: 10px 20px; /* Уменьшены padding кнопки на мобильных */
            }

            .modal-content {
                width: 90%; /* Модалка занимает большую часть ширины на мобильных */
                padding: 20px; /* Уменьшены padding модалки на мобильных */
                margin-top: 20%; /* Увеличен верхний отступ модалки на мобильных */
            }

            .close {
                font-size: 24px; /* Уменьшен размер крестика на мобильных */
            }
        }

        /* Стиль для галереи */
        .gallery {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            margin-top: 20px; /* Уменьшены отступы сверху для галереи */
        }

        .gallery img {
            width: 250px; /* Уменьшен размер изображений в галерее */
            height: 250px; /* Квадратные изображения */
            object-fit: cover;
            margin: 10px; /* Уменьшены отступы между изображениями галереи */
            border-radius: 6px; /* Менее скругленные углы изображений галереи */
            box-shadow: 0 3px 7px rgba(0, 0, 0, 0.15); /* Более легкая тень для изображений галереи */
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .gallery img:hover {
            transform: scale(1.05); /* Меньшее увеличение при наведении на изображения галереи */
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.25); /* Умеренная тень при наведении на изображения галереи */
        }

        /* Стиль для раздела "О тренере" */
        .about-trainer {
            margin-top: 40px; /* Уменьшены отступы сверху для раздела "О тренере" */
            text-align: center;
        }

        .about-trainer img {
            width: 200px; /* Уменьшен размер фото тренера */
            height: 200px;
            object-fit: cover;
            border-radius: 50%;
            box-shadow: 0 3px 7px rgba(0, 0, 0, 0.15); /* Более легкая тень для фото тренера */
            margin-bottom: 20px; /* Уменьшены отступы снизу для фото тренера */
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .about-trainer img:hover {
            transform: scale(1.03); /* Меньшее увеличение при наведении на фото тренера */
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.25); /* Умеренная тень при наведении на фото тренера */
        }

        .about-trainer p {
            max-width: 800px; /* Уменьшена максимальная ширина текста "О тренере" */
            margin: 0 auto;
            font-size: 1em; /* Уменьшен размер шрифта в разделе "О тренере" */
        }

        /* Стиль для отзывов клиентов */
        .testimonials {
            margin-top: 40px; /* Уменьшены отступы сверху для отзывов */
        }

        .testimonial {
            background-color: #fff; /* Белый фон для отзывов */
            padding: 20px; /* Уменьшены padding для отзывов */
            border-radius: 6px; /* Менее скругленные углы для отзывов */
            margin-bottom: 20px; /* Уменьшены отступы между отзывами */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Легкая тень для отзывов */
            border: 1px solid #eee; /* Легкая граница для отзывов */
        }

        .testimonial:hover {
            background-color: #f9f9f9; /* Ещё более светлый фон отзывов при наведении */
        }

        .testimonial p {
            font-style: italic;
            font-size: 1em; /* Уменьшен размер шрифта для текста отзыва */
            color: #666; /* Цвет текста отзыва */
        }

        .testimonial .author {
            font-weight: bold;
            margin-top: 10px; /* Уменьшены отступы сверху для имени автора отзыва */
            text-align: right;
            font-size: 0.9em; /* Уменьшен размер шрифта для имени автора отзыва */
            color: #777; /* Цвет имени автора отзыва */
        }
    </style>
</head>

<body>
    <div class="container">
        <h1>Данило - Персональный тренер в Киеве</h1> <p>Здравствуйте! Меня зовут <strong>Данило</strong>, и я ваш персональный тренер, готовый помочь вам достичь ваших целей в фитнесе.</p>

        <h2>Моя квалификация:</h2>
        <p>
            <span class="stats">🏆 Победитель чемпионата Украины</span>
            <span class="stats">🏋️ Опыт работы с атлетами любого уровня подготовки</span>
        </p>

        <h2>Силовые показатели:</h2>
        <p>
            <span class="stats">💪 Жим лёжа: 140 кг</span>
            <span class="stats">🏋️ Приседание: 220 кг</span>
            <span class="stats">🚀 Становая тяга: 250 кг</span>
        </p>

        <p><strong>Хотите начать тренировки уже сегодня?</strong></p>
        <a href="#" class="button" id="openModal">Записаться на тренировку</a>

        <div class="gallery">
            <img src="https://images.unsplash.com/photo-1517842744674-2904992f5978?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Фото Галереи Серия 1">
            <img src="https://images.unsplash.com/photo-1530177356825-5b1a33fa2898?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Фото Галереи Серия 2">
            <img src="https://images.unsplash.com/photo-1607962837359-ff3e96558742?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Фото Галереи Серия 3">
        </div>

        <div class="about-trainer">
            <h2>Обо мне</h2> <img src="https://images.unsplash.com/photo-1552726388-6e94d62eeaa4?q=80&w=1974&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D" alt="Фото Данило Тренер">
            <p>Приветствую! Я Данило, ваш персональный проводник в мир фитнеса и здорового образа жизни, и персональный тренер в Киеве. Моя цель - помочь вам раскрыть ваш потенциал и достичь желаемых результатов.  Обладая многолетним опытом и победами, я разработал эффективные программы, которые помогут вам не только изменить тело, но и почувствовать себя сильнее и энергичнее. Присоединяйтесь, и вместе мы создадим фигуру вашей мечты!</p>
        </div>

        <div class="testimonials">
            <h2>Отзывы</h2> <div class="testimonial">
                <p>"Данило - прекрасный тренер! С его помощью я сбросил вес и улучшил самочувствие. Тренировки всегда интересные и мотивирующие."</p>
                <p class="author">- Иван, 32 года</p>
            </div>
            <div class="testimonial">
                <p>"Занимаюсь с Данило и вижу отличный прогресс! Тело стало более подтянутым, появилась энергия. Рекомендую как профессионала своего дела."</p>
                <p class="author">- Елена, 28 лет</p>
            </div>
        </div>
    </div>

    <div id="modal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Запись на тренировку</h2> <form class="modal-form">
                <label for="name">Ваше имя:</label> <input type="text" id="name" name="name" required>

                <label for="email">Ваш Email:</label> <input type="email" id="email" name="email" required>

                <label for="phone">Ваш телефон:</label> <input type="tel" id="phone" name="phone">

                <label for="message">Комментарий (необязательно):</label>
                <textarea id="message" name="message"></textarea>

                <button type="submit">Отправить</button> </form>
        </div>
    </div>

    <script>
        // Модальное окно
        var modal = document.getElementById("modal");
        var btn = document.getElementById("openModal");
        var span = document.getElementsByClassName("close")[0];

        btn.onclick = function() {
            modal.style.display = "block";
        }

        span.onclick = function() {
            modal.style.display = "none";
        }

        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }
    </script>

</body>

</html>
