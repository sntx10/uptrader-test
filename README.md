# Project: Uptrader-Test

## 🚀 Preparation

- **Python 3.10.2**
  
### 🛠️ Installation

1. **Clone the repository:**
    ```bash
    git clone https://gitlab.com/dvtarkov/uptrader-test.git
    ```
2. **Installing dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3. **Applying migrations:**
    ```bash
    python manage.py migrate
    ```

### 🚀 Usage

!!! Unit tests for draw_menu are available at the command 
``python manage.py test menu_app.tests``.
Contains two tests - checking that the menu items are drawn and checking that the number of database queries does not exceed 1.

#### 📝 Menu creation

- Menus are created through the standard Django admin. Go to [admin page](http://localhost:8000/admin/menu_app/menu/), replacing http://localhost:8000 with your application's address. You can create a new menu by specifying its name and menu items. Menu items can be created in the admin or linked to existing models and their URLs.

#### 🖥️ Displaying menus

- To display the menu on the page, load the template tag:
    ```django
    {% load menu_tags %}
    ```
- Then, at the desired location, call:
    ```django
    {% draw_menu 'main_menu' %}
    ```
  Where 'main_menu' is the name of the menu. The draw_menu tag will create a tree menu based on the items created in the admin.

    - Everything above the highlighted item will be expanded. First level of nesting
