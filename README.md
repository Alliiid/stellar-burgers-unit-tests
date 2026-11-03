# Модульное тестирование приложения Stellar Burgers (Дипломная работа, Часть 1)

![Java](https://img.shields.io/badge/Java-11-orange?logo=java)
![Maven](https://img.shields.io/badge/Maven-Build-blue?logo=apache-maven)
![JUnit4](https://img.shields.io/badge/JUnit-4.13.2-red)
![Mockito](https://img.shields.io/badge/Mockito-Core-yellow)
![JaCoCo](https://img.shields.io/badge/JaCoCo-100%25_Coverage-brightgreen)

Первая часть дипломного проекта курса «Инженер по тестированию»: покрытие модульными (unit) тестами доменной логики сервиса сборки заказов космической бургерной `Stellar Burgers` с достижением 100% покрытия кода по метрикам JaCoCo.

---

## 📌 Ключевые архитектурные решения

- **Изоляция с Mockito:** Класс `Burger` протестирован в полной изоляции от реальных моделей булочек (`Bun`) и ингредиентов (`Ingredient`). Взаимодействия смоделированы с помощью мок-объектов (`@Mock`), стабов (`when().thenReturn()`) и верификаций вызовов.
- **Параметризация:** Проверка формулы расчета стоимости бургера вынесена в отдельный класс `BurgerPriceParameterizedTest` для тестирования различных комбинаций цен булочек и наборов ингредиентов.
- **100% Code Coverage:** Достигнуто полное покрытие тестами всех классов проекта, включая генерацию чека, перечисления (`IngredientType`) и имитацию хранилища (`Database`).

---

## 🧪 Реализованные тестовые наборы

* **`BurgerTest`:**
  - Установка булочек (`setBuns`);
  - Добавление и удаление ингредиентов (`addIngredient`, `removeIngredient`);
  - Изменение порядка ингредиентов в слоях бургера (`moveIngredient`);
  - Формирование текста чека (`getReceipt`) с корректными названиями и итоговой стоимостью.
* **`BurgerPriceParameterizedTest`:**
  - Параметризованная валидация формулы расчета стоимости: `(цена булки * 2) + сумма цен всех ингредиентов`.
* **`BunTest`:**
  - Инициализация объекта булки, корректный возврат названия и цены (`getName`, `getPrice`).
* **`IngredientTest`:**
  - Проверка геттеров типа, названия и стоимости ингредиента (`getType`, `getName`, `getPrice`).
* **`IngredientTypeTest`:**
  - Валидация значений перечисления (`SAUCE`, `FILLING`).
* **`DatabaseTest`:**
  - Проверка инициализации базы данных: корректное количество доступных булок (3 шт.) и ингредиентов (6 шт.).

---

## 🛠 Стек технологий

* **Язык программирования:** [Java 11](https://www.oracle.com/java/technologies/javase/jdk11-archive-downloads.html)
* **Система сборки:** [Apache Maven](https://maven.apache.org/)
* **Тестовый фреймворк:** [JUnit 4](https://junit.org/junit4/)
* **Библиотека мокирования:** [Mockito](https://site.mockito.org/)
* **Анализ покрытия кода:** [JaCoCo Plugin](https://www.eclemma.org/jacoco/)
