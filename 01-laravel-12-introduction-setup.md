---

# Laravel 12 Installation Cheatsheet (Linux)

Follow these steps to install and set up **Laravel 12** on Linux.

| Step                         | Command                                                                                                          | Explanation                                         |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------- |
| 1. Update & Upgrade          | `bash<br>sudo apt update && sudo apt upgrade -y<br>`                                                             | Updates system packages before installation.        |
| 2. Install PHP & Extensions  | `bash<br>sudo apt install php php-cli php-mbstring php-xml php-bcmath php-curl unzip curl git -y<br>`            | Installs PHP and required extensions for Laravel.   |
| 3. Install Composer          | `bash<br>curl -sS https://getcomposer.org/installer \| php<br>sudo mv composer.phar /usr/local/bin/composer<br>` | Installs Composer, Laravel’s dependency manager.    |
| 4. Verify Composer           | `bash<br>composer -v<br>`                                                                                        | Confirms Composer is installed globally.            |
| 5. Install Laravel Installer | `bash<br>composer global require laravel/installer<br>`                                                          | Installs Laravel installer globally.                |
| 6. Add Composer to PATH      | `bash<br>export PATH="$HOME/.composer/vendor/bin:$PATH"<br>`                                                     | Ensures Laravel installer is accessible everywhere. |
| 7. Create New Project        | `bash<br>laravel new project-name<br>` OR `bash<br>composer create-project laravel/laravel project-name<br>`     | Creates a new Laravel 12 project.                   |
| 8. Run Development Server    | `bash<br>cd project-name<br>php artisan serve<br>`                                                               | Starts Laravel server at `http://127.0.0.1:8000`.   |

---

✅ You’ve successfully set up **Laravel 12** on Linux!

📺 Watch the full video tutorial here:
👉 [Episode 01 – Introduction & Setup](https://youtube.com/playlist?list=PLsSvcd6n_RmnhPDl7Zs_tcpxn0VhxcUU_&si=9TlKJ5V_ym5uRy3z)

---
