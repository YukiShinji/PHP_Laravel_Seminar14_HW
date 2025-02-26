# Продвинутое программирование на PHP — Laravel
## Домашняя работа №14

---

Цели практической работы:

— Научиться интегрировать админ-панель в проект. \
— Разобраться в настройке CRUD-методов для сущности в voyager. \

Что нужно сделать:

В этой практической работе вы создадите панель администратора для склада интернет-магазина.

### 1. Создайте новый проект Laravel или откройте уже существующий.

---
![new project](storage/app/public/img/1_0.png "new project")
![new project](storage/app/public/img/1_1.png "new project")
![new project](storage/app/public/img/1_2.png "new project")
![new project](storage/app/public/img/1_3.png "new project")
![new project](storage/app/public/img/1_4.png "new project")
![new project](storage/app/public/img/1_5.png "new project")

---

### 2. Создайте новую ветку вашего репозитория от корневой (main или master).

---
![new branch](storage/app/public/img/2_0.png "new branch")
![new branch](storage/app/public/img/2_1.png "new branch")
![new branch](storage/app/public/img/2_2.png "new branch")

---

### 3. Создайте класс Category (модель, миграцию и контроллер) командой php artisan make:model Category -m

---
![Category](storage/app/public/img/3_0.png "Category")

---

### 4. Опишите миграцию для таблицы categories c типами полей:

```
$table->id();
$table->string('name');
$table->timestamps();
```

---
![Category migration](storage/app/public/img/4_0.png "Category migration")

---

### 5. Создайте класс Product (модель, миграцию и контроллер) командой php artisan make:model Product -m

---
![Product](storage/app/public/img/5_0.png "Product")

---

### 6. Опишите миграцию для таблицы products c типами полей:

```
$table->string('sku');
$table->id();
$table->string('sku');
$table->string('name');
$table->foreignId('category_id')->constrained();
```

---
![Product migration](storage/app/public/img/6_0.png "Product migration")

---

### 7. Выполните миграцию командой php artisan migrate

---
![migration](storage/app/public/img/7_0.png "migration")
![migration](storage/app/public/img/7_1.png "migration")
![migration](storage/app/public/img/7_2.png "migration")

---

### 8. Установите voyager командой composer require tcg/voyager

---
![composer require tcg/voyager](storage/app/public/img/8_0.png "composer require tcg/voyager")
![composer require tcg/voyager](storage/app/public/img/8_1.png "composer require tcg/voyager")

---

### 9. Выполните установку voyager внутри вашего приложения командой php artisan voyager:install

---
![php artisan voyager:install](storage/app/public/img/9_0.png "php artisan voyager:install")
![php artisan voyager:install](storage/app/public/img/9_1.png "php artisan voyager:install")

---

### 10. Создайте администратора вашего приложения командой php artisan voyager:admin your@email.com

---
![php artisan voyager:admin your@email.com](storage/app/public/img/10_0.png "php artisan voyager:admin your@email.com")

---

### 11. Войдите в панель администратора, перейдите во вкладку tools/bread и добавьте возможность редактирования сущностей category и product.

---
![tools/bread](storage/app/public/img/11_0.png "tools/bread")
![tools/bread](storage/app/public/img/11_1.png "tools/bread")
![tools/bread](storage/app/public/img/11_2.png "tools/bread")
![tools/bread](storage/app/public/img/11_3.png "tools/bread")
![tools/bread](storage/app/public/img/11_4.png "tools/bread")
![tools/bread](storage/app/public/img/11_5.png "tools/bread")
![tools/bread](storage/app/public/img/11_6.png "tools/bread")
---

### 12. После создания CRUD для сущности product перейдите в эту сущность и нажмите на кнопку Create A Relationship.

---
![Create A Relationship](storage/app/public/img/12_0.png "Create A Relationship")

---

### 13. Настройте связь следующим образом:

---
![relationship](storage/app/public/img/13_0.png "relationship")

---
    
### 14. Сохраните связь.

---
![saving relationship](storage/app/public/img/14_0.png "saving relationship")

---

### 15. Создайте категорию, а после — тестовый товар, прикреплённый к этой категории.

---
![create items](storage/app/public/img/15_0.png "create items")
![create items](storage/app/public/img/15_1.png "create items")
![create items](storage/app/public/img/15_2.png "create items")
![create items](storage/app/public/img/15_3.png "create items")

---

### 16. Создайте в проекте директорию App/Admin/Widgets и добавьте туда два виджета: ProductsWidget и CategoriesWidget.

---
![widgets](storage/app/public/img/16_0.png "widgets")

---

### 17. Реализуйте в этих виджетах счётчики количества товаров и категорий.

---
![widgets counts](storage/app/public/img/17_0.png "widgets counts")

---

### 18. Добавьте виджеты в конфигурационный файл voyager.php:

```
'widgets' => [
\App\Admin\Widgets\ProductsWidget::class,
\App\Admin\Widgets\CategoriesWidget::class,
],
```

---
![voyager.php](storage/app/public/img/18_0.png "voyager.php")
![voyager.php](storage/app/public/img/18_1.png "voyager.php")
![voyager.php](storage/app/public/img/18_2.png "voyager.php")
![voyager.php](storage/app/public/img/18_3.png "voyager.php")
![voyager.php](storage/app/public/img/18_4.png "voyager.php")

---
