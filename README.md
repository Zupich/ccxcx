<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Регистрация - Моя семья – мой космос</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* Общие стили */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        :root {
            --primary: #6C63FF;
            --secondary: #FF6584;
            --dark-bg: #121212;
            --dark-card: #1E1E1E;
            --dark-text: #E0E0E0;
            --dark-border: #333333;
            --error: #ff4757;
            --success: #2ed573;
        }

        body {
            background-color: var(--dark-bg);
            color: var(--dark-text);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        .container {
            width: 100%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Шапка сайта */
        header {
            background-color: rgba(18, 18, 18, 0.95);
            position: sticky;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }

        .logo {
            display: flex;
            align-items: center;
            text-decoration: none;
            color: var(--dark-text);
        }

        .logo-icon {
            font-size: 28px;
            margin-right: 10px;
            color: var(--primary);
        }

        .logo-text {
            font-size: 22px;
            font-weight: 700;
        }

        .logo-text span {
            color: var(--secondary);
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 25px;
        }

        nav ul li a {
            color: var(--dark-text);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s;
        }

        nav ul li a:hover {
            color: var(--primary);
        }

        .theme-toggle {
            background: none;
            border: none;
            color: var(--dark-text);
            font-size: 20px;
            cursor: pointer;
            margin-left: 20px;
        }

        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: var(--dark-text);
            font-size: 24px;
            cursor: pointer;
        }

        /* Основной контент */
        .main-content {
            flex: 1;
            padding: 40px 0;
        }

        .page-title {
            text-align: center;
            margin-bottom: 40px;
            font-size: 36px;
            position: relative;
        }

        .page-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--primary);
            margin: 15px auto 0;
        }

        /* Форма регистрации */
        .registration-container {
            display: flex;
            justify-content: center;
        }

        .registration-form {
            background-color: var(--dark-card);
            padding: 40px;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
            width: 100%;
            max-width: 800px;
        }

        .form-section {
            margin-bottom: 30px;
            padding-bottom: 20px;
            border-bottom: 1px solid var(--dark-border);
        }

        .section-title {
            font-size: 22px;
            margin-bottom: 20px;
            color: var(--primary);
            display: flex;
            align-items: center;
        }

        .section-title i {
            margin-right: 10px;
        }

        .form-row {
            display: flex;
            flex-wrap: wrap;
            margin: 0 -10px;
        }

        .form-group {
            flex: 1 0 300px;
            margin: 0 10px 20px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
        }

        .form-control {
            width: 100%;
            padding: 12px 15px;
            background-color: #2a2a2a;
            border: 1px solid var(--dark-border);
            border-radius: 5px;
            color: var(--dark-text);
            font-size: 16px;
            transition: border-color 0.3s;
        }

        .form-control:focus {
            outline: none;
            border-color: var(--primary);
        }

        .form-control.error {
            border-color: var(--error);
        }

        .form-control.success {
            border-color: var(--success);
        }

        .error-message {
            color: var(--error);
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }

        .success-message {
            color: var(--success);
            font-size: 14px;
            margin-top: 5px;
            display: none;
        }

        .age-inputs {
            display: flex;
            gap: 15px;
        }

        .age-inputs .form-group {
            flex: 1;
        }

        .radio-group {
            display: flex;
            gap: 20px;
            margin-top: 5px;
        }

        .radio-option {
            display: flex;
            align-items: center;
        }

        .radio-option input {
            margin-right: 8px;
        }

        .file-upload {
            border: 2px dashed var(--dark-border);
            border-radius: 5px;
            padding: 30px;
            text-align: center;
            cursor: pointer;
            transition: border-color 0.3s;
        }

        .file-upload:hover {
            border-color: var(--primary);
        }

        .file-upload i {
            font-size: 40px;
            margin-bottom: 15px;
            color: var(--primary);
        }

        .file-upload p {
            margin-bottom: 10px;
        }

        .file-upload small {
            color: #888;
        }

        .checkbox-group {
            display: flex;
            align-items: flex-start;
            margin-bottom: 20px;
        }

        .checkbox-group input {
            margin-right: 10px;
            margin-top: 5px;
        }

        .checkbox-group label {
            font-size: 14px;
            color: #aaa;
        }

        .checkbox-group a {
            color: var(--primary);
            text-decoration: none;
        }

        .checkbox-group a:hover {
            text-decoration: underline;
        }

        .form-actions {
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }

        .btn {
            display: inline-block;
            padding: 12px 25px;
            background-color: var(--primary);
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            font-size: 16px;
        }

        .btn:hover {
            background-color: #5752d4;
            transform: translateY(-2px);
        }

        .btn-large {
            padding: 15px 40px;
            font-size: 18px;
        }

        /* Секция членов семьи */
        .family-members {
            margin-top: 30px;
        }

        .member-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .member-actions {
            display: flex;
            gap: 10px;
        }

        .btn-secondary {
            background-color: var(--secondary);
        }

        .btn-secondary:hover {
            background-color: #e05575;
        }

        .btn-outline {
            background-color: transparent;
            border: 1px solid var(--dark-border);
            color: var(--dark-text);
        }

        .btn-outline:hover {
            background-color: rgba(255, 255, 255, 0.05);
        }

        .member-fields {
            display: none;
            background-color: rgba(42, 42, 42, 0.5);
            padding: 20px;
            border-radius: 5px;
            margin-bottom: 20px;
        }

        .member-fields.active {
            display: block;
        }

        /* Сообщения о статусе формы */
        .form-status {
            padding: 15px;
            border-radius: 5px;
            margin-bottom: 20px;
            display: none;
        }

        .form-status.success {
            background-color: rgba(46, 213, 115, 0.2);
            border: 1px solid var(--success);
            color: var(--success);
        }

        .form-status.error {
            background-color: rgba(255, 71, 87, 0.2);
            border: 1px solid var(--error);
            color: var(--error);
        }

        .form-status.warning {
            background-color: rgba(255, 165, 0, 0.2);
            border: 1px solid orange;
            color: orange;
        }

        /* Подвал сайта */
        footer {
            background-color: #0a0a0a;
            padding: 40px 0 20px;
            margin-top: 60px;
        }

        .footer-container {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        .footer-column {
            flex: 1;
            min-width: 200px;
            margin-bottom: 30px;
        }

        .footer-title {
            font-size: 18px;
            margin-bottom: 20px;
            color: var(--dark-text);
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 10px;
        }

        .footer-links a {
            color: #aaa;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-links a:hover {
            color: var(--primary);
        }

        .contact-info {
            color: #aaa;
        }

        .contact-info p {
            margin-bottom: 10px;
        }

        .contact-info a {
            color: #aaa;
            text-decoration: none;
        }

        .contact-info a:hover {
            color: var(--primary);
        }

        .copyright {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid var(--dark-border);
            color: #777;
            font-size: 14px;
        }

        /* Адаптивность */
        @media (max-width: 768px) {
            .header-container {
                flex-wrap: wrap;
            }
            
            nav {
                display: none;
                width: 100%;
                margin-top: 15px;
            }
            
            nav.active {
                display: block;
            }
            
            nav ul {
                flex-direction: column;
            }
            
            nav ul li {
                margin: 10px 0;
            }
            
            .mobile-menu-btn {
                display: block;
            }
            
            .registration-form {
                padding: 25px;
            }
            
            .form-group {
                flex: 1 0 100%;
            }
            
            .age-inputs {
                flex-direction: column;
                gap: 0;
            }
            
            .footer-column {
                flex: 0 0 100%;
            }
        }

        @media (max-width: 576px) {
            .page-title {
                font-size: 28px;
            }
            
            .section-title {
                font-size: 20px;
            }
            
            .member-header {
                flex-direction: column;
                align-items: flex-start;
                gap: 15px;
            }
            
            .member-actions {
                width: 100%;
                justify-content: space-between;
            }
        }
    </style>
</head>
<body>
    <!-- Шапка сайта -->
    <header>
        <div class="container header-container">
            <a href="index.html" class="logo">
                <div class="logo-icon"><i class="fas fa-rocket"></i></div>
                <div class="logo-text">Моя семья – <span>мой космос</span></div>
            </a>
            
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            
            <nav>
                <ul>
                    <li><a href="index.html">Главная</a></li>
                    <li><a href="index.html#auth">Авторизация</a></li>
                    <li><a href="account.html">Личный кабинет</a></li>
                    <li><a href="index.html#about">О нас</a></li>
                    <li><a href="index.html#competitions">Конкурсы</a></li>
                    <li><a href="schedule.html">Расписание</a></li>
                    <li>
                        <button class="theme-toggle">
                            <i class="fas fa-moon"></i>
                        </button>
                    </li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Основной контент -->
    <main class="main-content">
        <div class="container">
            <h1 class="page-title">Регистрация на сайте</h1>
            
            <div class="registration-container">
                <form class="registration-form" id="registrationForm">
                    <!-- Сообщения о статусе формы -->
                    <div class="form-status success" id="successMessage">
                        <i class="fas fa-check-circle"></i> Все данные заполнены корректно!
                    </div>
                    
                    <div class="form-status error" id="errorMessage">
                        <i class="fas fa-exclamation-circle"></i> Пожалуйста, исправьте ошибки в форме.
                    </div>
                    
                    <div class="form-status warning" id="warningMessage">
                        <i class="fas fa-exclamation-triangle"></i> Пожалуйста, заполните все обязательные поля.
                    </div>
                    
                    <!-- Основные данные пользователя -->
                    <div class="form-section">
                        <h2 class="section-title"><i class="fas fa-user"></i> Основные данные</h2>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="email">Электронная почта *</label>
                                <input type="email" id="email" class="form-control" placeholder="example@mail.ru" required>
                                <div class="error-message" id="emailError">Пожалуйста, введите корректный email</div>
                                <div class="success-message" id="emailSuccess">Email корректен</div>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="firstName">Имя *</label>
                                <input type="text" id="firstName" class="form-control" placeholder="Введите ваше имя" required>
                                <div class="error-message" id="firstNameError">Имя должно содержать только буквы</div>
                                <div class="success-message" id="firstNameSuccess">Имя корректно</div>
                            </div>
                            
                            <div class="form-group">
                                <label for="lastName">Фамилия *</label>
                                <input type="text" id="lastName" class="form-control" placeholder="Введите вашу фамилию" required>
                                <div class="error-message" id="lastNameError">Фамилия должна содержать только буквы</div>
                                <div class="success-message" id="lastNameSuccess">Фамилия корректна</div>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="age">Возраст *</label>
                                <div class="age-inputs">
                                    <div class="form-group">
                                        <input type="number" id="age" class="form-control" placeholder="Лет" min="1" max="120" required>
                                    </div>
                                    <div class="form-group">
                                        <select id="ageRange" class="form-control">
                                            <option value="">Выберите диапазон</option>
                                            <option value="0-12">0-12 лет</option>
                                            <option value="13-17">13-17 лет</option>
                                            <option value="18-25">18-25 лет</option>
                                            <option value="26-35">26-35 лет</option>
                                            <option value="36-50">36-50 лет</option>
                                            <option value="51+">51+ лет</option>
                                        </select>
                                    </div>
                                </div>
                                <div class="error-message" id="ageError">Пожалуйста, укажите возраст</div>
                                <div class="success-message" id="ageSuccess">Возраст указан</div>
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label>Пол *</label>
                                <div class="radio-group">
                                    <div class="radio-option">
                                        <input type="radio" id="male" name="gender" value="male" required>
                                        <label for="male">Мужской</label>
                                    </div>
                                    <div class="radio-option">
                                        <input type="radio" id="female" name="gender" value="female" required>
                                        <label for="female">Женский</label>
                                    </div>
                                </div>
                                <div class="error-message" id="genderError">Пожалуйста, выберите пол</div>
                                <div class="success-message" id="genderSuccess">Пол выбран</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Пароль -->
                    <div class="form-section">
                        <h2 class="section-title"><i class="fas fa-lock"></i> Безопасность</h2>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="password">Пароль *</label>
                                <input type="password" id="password" class="form-control" placeholder="Придумайте пароль" required>
                                <div class="error-message" id="passwordError">Пароль должен содержать не менее 8 символов</div>
                                <div class="success-message" id="passwordSuccess">Пароль надежен</div>
                            </div>
                            
                            <div class="form-group">
                                <label for="confirmPassword">Повтор пароля *</label>
                                <input type="password" id="confirmPassword" class="form-control" placeholder="Повторите пароль" required>
                                <div class="error-message" id="confirmPasswordError">Пароли не совпадают</div>
                                <div class="success-message" id="confirmPasswordSuccess">Пароли совпадают</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Семейная фотография -->
                    <div class="form-section">
                        <h2 class="section-title"><i class="fas fa-camera"></i> Семейная фотография</h2>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <div class="file-upload" id="fileUpload">
                                    <i class="fas fa-cloud-upload-alt"></i>
                                    <p>Загрузите семейную фотографию</p>
                                    <small>JPG, PNG или GIF, не более 5MB</small>
                                    <input type="file" id="familyPhoto" accept="image/*" style="display: none;">
                                </div>
                                <div class="error-message" id="photoError">Пожалуйста, загрузите фотографию</div>
                                <div class="success-message" id="photoSuccess">Фотография загружена</div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Члены семьи -->
                    <div class="form-section">
                        <h2 class="section-title"><i class="fas fa-users"></i> Члены семьи</h2>
                        
                        <div class="family-members">
                            <div class="member-header">
                                <h3>Добавить члена семьи</h3>
                                <div class="member-actions">
                                    <button type="button" class="btn btn-secondary" id="addMemberBtn">
                                        <i class="fas fa-plus"></i> Добавить
                                    </button>
                                    <button type="button" class="btn btn-outline" id="removeMemberBtn" disabled>
                                        <i class="fas fa-minus"></i> Удалить
                                    </button>
                                </div>
                            </div>
                            
                            <div class="member-fields" id="memberFields">
                                <div class="form-row">
                                    <div class="form-group">
                                        <label for="memberLastName">Фамилия</label>
                                        <input type="text" id="memberLastName" class="form-control" placeholder="Фамилия члена семьи">
                                    </div>
                                    
                                    <div class="form-group">
                                        <label for="memberFirstName">Имя</label>
                                        <input type="text" id="memberFirstName" class="form-control" placeholder="Имя члена семьи">
                                    </div>
                                </div>
                                
                                <div class="form-row">
                                    <div class="form-group">
                                        <label for="memberAge">Возраст</label>
                                        <input type="number" id="memberAge" class="form-control" placeholder="Возраст" min="0" max="120">
                                    </div>
                                    
                                    <div class="form-group">
                                        <label for="memberGender">Пол</label>
                                        <select id="memberGender" class="form-control">
                                            <option value="">Выберите пол</option>
                                            <option value="male">Мужской</option>
                                            <option value="female">Женский</option>
                                        </select>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                    
                    <!-- Согласие на обработку данных -->
                    <div class="form-section">
                        <div class="checkbox-group">
                            <input type="checkbox" id="agree" required>
                            <label for="agree">Я согласен на обработку моих персональных данных в соответствии с <a href="#">политикой конфиденциальности</a> *</label>
                        </div>
                        <div class="error-message" id="agreeError">Необходимо ваше согласие</div>
                    </div>
                    
                    <!-- Кнопка регистрации -->
                    <div class="form-actions">
                        <button type="submit" class="btn btn-large">Зарегистрироваться</button>
                    </div>
                </form>
            </div>
        </div>
    </main>

    <!-- Подвал сайта -->
    <footer>
        <div class="container">
            <div class="footer-container">
                <div class="footer-column">
                    <h3 class="footer-title">Контакты</h3>
                    <div class="contact-info">
                        <p><i class="fas fa-phone"></i> <a href="tel:+74842234567">+7 (4842) 23-45-67</a></p>
                        <p><i class="fas fa-envelope"></i> <a href="mailto:family@cosmos.ru">family@cosmos.ru</a></p>
                    </div>
                </div>
                
                <div class="footer-column">
                    <h3 class="footer-title">Навигация</h3>
                    <ul class="footer-links">
                        <li><a href="index.html">Главная</a></li>
                        <li><a href="index-light.html">Главная-светлая</a></li>
                        <li><a href="registration.html">Регистрация</a></li>
                        <li><a href="competition.html">Конкурс</a></li>
                        <li><a href="account.html">Личный кабинет</a></li>
                        <li><a href="404.html">Страница не найдена</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3 class="footer-title">О нас</h3>
                    <p>Мы создаем мероприятия, которые объединяют семьи и помогают им открывать новые горизонты вместе.</p>
                </div>
            </div>
            
            <div class="copyright">
                <p>&copy; 2023 "Моя семья – мой космос". Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Мобильное меню
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            document.querySelector('nav').classList.toggle('active');
        });

        // Загрузка файла
        document.getElementById('fileUpload').addEventListener('click', function() {
            document.getElementById('familyPhoto').click();
        });

        // Добавление/удаление полей для членов семьи
        document.getElementById('addMemberBtn').addEventListener('click', function() {
            document.getElementById('memberFields').classList.add('active');
            document.getElementById('removeMemberBtn').disabled = false;
        });

        document.getElementById('removeMemberBtn').addEventListener('click', function() {
            document.getElementById('memberFields').classList.remove('active');
            document.getElementById('removeMemberBtn').disabled = true;
            
            // Очистка полей
            document.getElementById('memberLastName').value = '';
            document.getElementById('memberFirstName').value = '';
            document.getElementById('memberAge').value = '';
            document.getElementById('memberGender').value = '';
        });

        // Валидация формы (упрощенная демонстрация)
        document.getElementById('registrationForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // В реальном проекте здесь была бы полноценная валидация
            // Для демонстрации просто показываем сообщение об успехе
            document.getElementById('successMessage').style.display = 'block';
            document.getElementById('errorMessage').style.display = 'none';
            document.getElementById('warningMessage').style.display = 'none';
        });
    </script>
</body>
</html>
