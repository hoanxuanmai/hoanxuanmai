- [**1. Tối Ưu Hiệu Suất Composer**](#1-tối-ưu-hiệu-suất-composer)
    - [**Tạo file `composer.lock` để cố định phiên bản**](#tạo-file-composerlock-để-cố-định-phiên-bản)
    - [**Preloading Classmap để tăng tốc**](#preloading-classmap-để-tăng-tốc)
  - [**2. Quản Lý Dependency Hiệu Quả**](#2-quản-lý-dependency-hiệu-quả)
    - [**Giới hạn phạm vi cài đặt của Composer**](#giới-hạn-phạm-vi-cài-đặt-của-composer)
    - [**Sử dụng các repository thay thế**](#sử-dụng-các-repository-thay-thế)
  - [**3. Tự Định Nghĩa Autoload**](#3-tự-định-nghĩa-autoload)
  - [**4. Tạo Package Composer Riêng**](#4-tạo-package-composer-riêng)
    - [**Tạo cấu trúc thư mục**](#tạo-cấu-trúc-thư-mục)
  - [**5. Composer Hooks \& CI/CD**](#5-composer-hooks--cicd)
  - [**6. Sử Dụng Composer với Private Repository**](#6-sử-dụng-composer-với-private-repository)
  - [**7. Debug và Kiểm Tra Composer**](#7-debug-và-kiểm-tra-composer)
    - [**Kiểm tra phiên bản gói trong dự án**](#kiểm-tra-phiên-bản-gói-trong-dự-án)
    - [**Kiểm tra lỗi trong dependency**](#kiểm-tra-lỗi-trong-dependency)
    - [**Phân tích dependency tree**](#phân-tích-dependency-tree)
  - [**8. Composer Patch và Fork Package**](#8-composer-patch-và-fork-package)
    - [**Patch một package mà không cần sửa source**](#patch-một-package-mà-không-cần-sửa-source)
    - [**Fork một package và sử dụng phiên bản tùy chỉnh**](#fork-một-package-và-sử-dụng-phiên-bản-tùy-chỉnh)
  - [**Tóm Tắt**](#tóm-tắt)
- [**Local Package**](#local-package)
  - [**1. Cấu Hình Local Package**](#1-cấu-hình-local-package)
  - [**2. Cấu Hình `composer.json` Cho Local Package**](#2-cấu-hình-composerjson-cho-local-package)
  - [**3. Cài Đặt \& Kiểm Tra**](#3-cài-đặt--kiểm-tra)
    - [**Cài đặt package trong dự án chính**](#cài-đặt-package-trong-dự-án-chính)
    - [**Tải thư viện trong dự án chính**](#tải-thư-viện-trong-dự-án-chính)
  - [**4. Chế Độ Symlink vs Copy**](#4-chế-độ-symlink-vs-copy)
  - [**5. Debug \& Kiểm Tra**](#5-debug--kiểm-tra)
  - [**6. Khi Nào Dùng Local Package?**](#6-khi-nào-dùng-local-package)
- [**Kiến thức nâng cao khác**](#kiến-thức-nâng-cao-khác)
  - [**1. Caching và Performance Optimization**](#1-caching-và-performance-optimization)
    - [**Cache Composer để tăng tốc độ cài đặt**](#cache-composer-để-tăng-tốc-độ-cài-đặt)
  - [**2. Composer Plugin và Extension**](#2-composer-plugin-và-extension)
  - [**3. Sử Dụng Composer Để Quản Lý Script**](#3-sử-dụng-composer-để-quản-lý-script)
  - [**4. Tích Hợp Composer Với Laravel, Symfony, WordPress**](#4-tích-hợp-composer-với-laravel-symfony-wordpress)
    - [**Laravel**](#laravel)
    - [**Symfony**](#symfony)
    - [**WordPress**](#wordpress)
  - [**5. Composer và Private Repository**](#5-composer-và-private-repository)
    - [**1. Packagist Private**](#1-packagist-private)
    - [**2. Satis – Tạo Packagist Private**](#2-satis--tạo-packagist-private)
  - [**6. Debug Composer**](#6-debug-composer)
  - [**7. Composer và Git Submodule**](#7-composer-và-git-submodule)
  - [**8. Cấu Hình Advanced Trong `composer.json`**](#8-cấu-hình-advanced-trong-composerjson)
    - [**Thiết lập phiên bản PHP yêu cầu**](#thiết-lập-phiên-bản-php-yêu-cầu)
    - [**Giới hạn số lượng package song song khi cài đặt**](#giới-hạn-số-lượng-package-song-song-khi-cài-đặt)
  - [**9. Composer Audit – Kiểm Tra Bảo Mật**](#9-composer-audit--kiểm-tra-bảo-mật)
  - [**10. Kết Hợp Composer Với Docker**](#10-kết-hợp-composer-với-docker)
  - [**Tóm Tắt**](#tóm-tắt-1)

---

# **1. Tối Ưu Hiệu Suất Composer**
### **Tạo file `composer.lock` để cố định phiên bản**
Khi làm việc với một nhóm, hãy cam kết tệp `composer.lock` vào Git để đảm bảo tất cả thành viên sử dụng cùng phiên bản thư viện.
```sh
composer install --prefer-dist --no-dev --optimize-autoloader
```
Tùy chọn:
- `--prefer-dist`: Tải về file zip thay vì clone từ Git (nhanh hơn).
- `--no-dev`: Không cài đặt thư viện dành cho development.
- `--optimize-autoloader`: Tăng tốc autoloading.

---

### **Preloading Classmap để tăng tốc**
Tạo file `classmap.php` giúp tăng tốc độ autoload:
```sh
composer dump-autoload --classmap-authoritative
```
Tùy chọn:
- `--classmap-authoritative`: Bỏ qua `PSR-4`, chỉ sử dụng `classmap` để tăng tốc.
- `--no-dev`: Không load class trong development dependencies.

---

## **2. Quản Lý Dependency Hiệu Quả**
### **Giới hạn phạm vi cài đặt của Composer**
Nếu bạn muốn chắc chắn chỉ sử dụng các dependency ổn định:
```sh
composer config minimum-stability stable
```
Hoặc nếu bạn muốn hỗ trợ beta:
```sh
composer config minimum-stability beta
```

### **Sử dụng các repository thay thế**
Composer mặc định tải package từ Packagist, nhưng bạn có thể dùng một repository khác:
```json
"repositories": [
    {
        "type": "composer",
        "url": "https://repo.example.com"
    }
]
```
Hoặc chỉ định một package từ GitHub/GitLab:
```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/vendor/package"
    }
]
```
Cài đặt package từ GitHub:
```sh
composer require vendor/package:dev-master --prefer-source
```

---

## **3. Tự Định Nghĩa Autoload**
Bạn có thể định nghĩa autoload riêng cho dự án:
```json
"autoload": {
    "psr-4": {
        "App\\": "src/"
    },
    "files": ["src/helpers.php"]
}
```
Cập nhật autoload:
```sh
composer dump-autoload
```

---

## **4. Tạo Package Composer Riêng**
### **Tạo cấu trúc thư mục**
Tạo một thư viện riêng bằng Composer:
```sh
composer init
```
Điền thông tin package, sau đó thêm vào `autoload`:
```json
"autoload": {
    "psr-4": {
        "MyLibrary\\": "src/"
    }
}
```
Ví dụ, thư viện có cấu trúc:
```
my-library/
│── src/
│   ├── MyClass.php
│── composer.json
```
File `src/MyClass.php`:
```php
namespace MyLibrary;

class MyClass {
    public function sayHello() {
        return "Hello from MyLibrary!";
    }
}
```
Sau đó, cài đặt thư viện vào dự án khác bằng lệnh:
```sh
composer require myvendor/mylibrary
```

---

## **5. Composer Hooks & CI/CD**
Bạn có thể thêm **hooks** vào `composer.json` để chạy script sau khi cài đặt hoặc cập nhật:
```json
"scripts": {
    "pre-update-cmd": "php scripts/pre-update.php",
    "post-update-cmd": "php scripts/post-update.php"
}
```

Trong CI/CD (GitHub Actions, GitLab CI/CD), tối ưu Composer bằng cách cache lại các thư viện:
```yaml
jobs:
  build:
    steps:
      - name: Cache Composer dependencies
        uses: actions/cache@v2
        with:
          path: ~/.composer/cache
          key: composer-${{ hashFiles('**/composer.lock') }}
```

---

## **6. Sử Dụng Composer với Private Repository**
Nếu bạn có private package, hãy sử dụng **Private Packagist**, **Satis**, hoặc GitHub Packages:
```json
"repositories": [
    {
        "type": "composer",
        "url": "https://repo.packagist.com/mycompany/"
    }
]
```
Đăng nhập vào Private Packagist:
```sh
composer config --global http-basic.repo.packagist.com myusername mypassword
```

---

## **7. Debug và Kiểm Tra Composer**
### **Kiểm tra phiên bản gói trong dự án**
```sh
composer show
composer show monolog/monolog
```

### **Kiểm tra lỗi trong dependency**
```sh
composer validate
composer diagnose
```

### **Phân tích dependency tree**
```sh
composer depends monolog/monolog
```

---

## **8. Composer Patch và Fork Package**
### **Patch một package mà không cần sửa source**
Nếu bạn muốn thay đổi code của một package mà không fork, có thể dùng **composer-patches**:
```sh
composer require cweagans/composer-patches
```
Sau đó thêm patch vào `composer.json`:
```json
"extra": {
    "patches": {
        "monolog/monolog": [
            {
                "title": "Fix log format issue",
                "url": "https://example.com/patches/monolog-fix.patch"
            }
        ]
    }
}
```
Áp dụng patch:
```sh
composer install
```

### **Fork một package và sử dụng phiên bản tùy chỉnh**
Thay vì dùng package chính thức, bạn có thể fork repository trên GitHub, sau đó trỏ Composer vào repo fork:
```json
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/myforkeduser/monolog"
    }
],
"require": {
    "monolog/monolog": "dev-main"
}
```

---

## **Tóm Tắt**
✔️ **Tối ưu Composer** bằng `classmap`, `--optimize-autoloader` và `--no-dev`  
✔️ **Quản lý dependency thông minh** với `minimum-stability`, `repositories` và `config`  
✔️ **Tạo và quản lý package riêng**, publish lên Packagist hoặc sử dụng Private Repository  
✔️ **Tích hợp Composer vào CI/CD**, cache dependency để build nhanh hơn  
✔️ **Debug Composer** với `composer diagnose`, `composer depends`  
✔️ **Fork & Patch package** mà không cần đợi bản cập nhật chính thức  
Nếu bạn muốn sử dụng **local package** trong Composer (tức là package nằm trong thư mục cục bộ thay vì tải từ Packagist hay GitHub), bạn có thể sử dụng `path repository`. Điều này hữu ích khi bạn phát triển một thư viện riêng và muốn thử nghiệm mà không cần publish lên Packagist.

---
# **Local Package**
## **1. Cấu Hình Local Package**
Giả sử bạn có một dự án chính (`my-project/`) và một thư viện riêng (`my-library/`) nằm trong cùng một thư mục cha:

```
/projects
│── my-project/
│   ├── composer.json
│   ├── vendor/
│── my-library/
│   ├── composer.json
│   ├── src/
│   ├── MyLibrary/
│   │   ├── MyClass.php
```

Bạn có thể khai báo thư viện `my-library/` như một package cục bộ bằng cách thêm vào `composer.json` của **dự án chính (`my-project/`)**:

```json
"repositories": [
    {
        "type": "path",
        "url": "../my-library",
        "options": {
            "symlink": true
        }
    }
],
"require": {
    "myvendor/mylibrary": "*"
}
```

- **`"url": "../my-library"`**: Trỏ đến thư mục local chứa package.
- **`"symlink": true`**: Composer sẽ tạo symlink thay vì sao chép thư viện (giúp dễ dàng sửa code mà không cần cài lại).

---

## **2. Cấu Hình `composer.json` Cho Local Package**
Trong thư viện `my-library/`, bạn cần có tệp `composer.json` hợp lệ:

```json
{
    "name": "myvendor/mylibrary",
    "description": "My custom local library",
    "type": "library",
    "autoload": {
        "psr-4": {
            "MyLibrary\\": "src/"
        }
    },
    "require": {}
}
```

Sau đó, trong `my-library/src/MyLibrary/MyClass.php`:
```php
namespace MyLibrary;

class MyClass {
    public function hello() {
        return "Hello from MyLibrary!";
    }
}
```

---

## **3. Cài Đặt & Kiểm Tra**
### **Cài đặt package trong dự án chính**
Chạy lệnh trong `my-project/`:
```sh
composer require myvendor/mylibrary
```

Nếu đã cài đặt trước đó mà có thay đổi code, bạn có thể chạy:
```sh
composer update myvendor/mylibrary
```

### **Tải thư viện trong dự án chính**
Trong `my-project/index.php`:
```php
require 'vendor/autoload.php';

use MyLibrary\MyClass;

$myClass = new MyClass();
echo $myClass->hello(); // "Hello from MyLibrary!"
```

---

## **4. Chế Độ Symlink vs Copy**
Nếu `symlink: true`, Composer sẽ tạo một liên kết symbol (shortcut) tới thư mục gốc của package (`my-library/`), giúp bạn có thể chỉnh sửa code ngay lập tức mà không cần cài đặt lại.

Nếu bạn không muốn dùng symlink (trong trường hợp cần kiểm tra độc lập), có thể đặt `symlink: false` hoặc bỏ qua phần `options`.

---

## **5. Debug & Kiểm Tra**
- Kiểm tra xem package local có được nhận diện không:
  ```sh
  composer show myvendor/mylibrary
  ```
- Nếu có lỗi không nhận diện được package, thử chạy:
  ```sh
  composer dump-autoload
  ```

---

## **6. Khi Nào Dùng Local Package?**
✅ Khi phát triển thư viện riêng trước khi publish lên Packagist.  
✅ Khi làm việc với nhiều dự án nhưng muốn quản lý một thư viện chung mà không cần liên tục commit/push lên GitHub.  
✅ Khi cần chỉnh sửa một package mà không muốn fork hoặc patch.  

---

# **Kiến thức nâng cao khác**
---

## **1. Caching và Performance Optimization**
### **Cache Composer để tăng tốc độ cài đặt**
Mặc định, Composer lưu cache tại:
- Linux/macOS: `~/.composer/cache`
- Windows: `%APPDATA%\Composer\cache`

Bạn có thể kiểm tra cache hiện tại:
```sh
composer config cache-dir
```
Xóa cache nếu cần:
```sh
composer clear-cache
```

Trong CI/CD, cache Composer để giảm thời gian build:
```sh
composer install --prefer-dist --no-interaction --no-progress
```

---

## **2. Composer Plugin và Extension**
Bạn có thể mở rộng Composer bằng các plugin. Ví dụ:
- [`composer/composer`](https://github.com/composer/composer) – Cung cấp API để thao tác với Composer.
- [`hirak/prestissimo`](https://github.com/hirak/prestissimo) – Tải gói song song (đã bị deprecated, nhưng có thể thay bằng Composer v2).
- [`cweagans/composer-patches`](https://github.com/cweagans/composer-patches) – Hỗ trợ patching package.

Cài đặt plugin:
```sh
composer global require hirak/prestissimo
```

Nếu muốn tạo plugin riêng, bạn cần implement `Composer\Plugin\PluginInterface`.

---

## **3. Sử Dụng Composer Để Quản Lý Script**
Bạn có thể thêm các script tùy chỉnh vào `composer.json`:
```json
"scripts": {
    "start": "php -S localhost:8000 -t public",
    "test": "phpunit",
    "deploy": [
        "@test",
        "git push origin main",
        "php artisan migrate --force"
    ]
}
```
Chạy lệnh:
```sh
composer run-script deploy
```

---

## **4. Tích Hợp Composer Với Laravel, Symfony, WordPress**
### **Laravel**
Laravel sử dụng Composer để quản lý toàn bộ framework:
```sh
composer create-project --prefer-dist laravel/laravel myapp
```
Tối ưu autoload trong Laravel:
```sh
composer dump-autoload --optimize
```

### **Symfony**
```sh
composer create-project symfony/skeleton myapp
```
Tối ưu performance trong Symfony bằng `composer dump-env prod`.

### **WordPress**
WordPress có thể sử dụng Composer để quản lý plugin và theme:
```json
"repositories": [
    {
        "type": "composer",
        "url": "https://wpackagist.org"
    }
],
"require": {
    "wpackagist-plugin/woocommerce": "^7.0",
    "wpackagist-theme/astra": "^3.0"
}
```

---

## **5. Composer và Private Repository**
Nếu bạn có thư viện nội bộ hoặc muốn bảo vệ package riêng, có thể dùng:
### **1. Packagist Private**
[Packagist.com](https://packagist.com/) hỗ trợ private repository cho công ty.

### **2. Satis – Tạo Packagist Private**
[Satis](https://github.com/composer/satis) là một công cụ giúp bạn tạo một repository riêng:
```sh
composer create-project composer/satis --stability=dev --keep-vcs
```
Cấu hình `satis.json`:
```json
{
    "name": "My Private Repo",
    "homepage": "https://my-repo.com",
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/mycompany/mypackage.git"
        }
    ],
    "require": {
        "mycompany/mypackage": "*"
    }
}
```
Sau đó, chạy:
```sh
php bin/satis build satis.json public/
```
Và truy cập `public/index.html` để xem repository.

---

## **6. Debug Composer**
Nếu gặp lỗi với dependency, bạn có thể debug:
```sh
composer diagnose
composer why monolog/monolog
composer depends monolog/monolog
```

---

## **7. Composer và Git Submodule**
Nếu bạn không muốn sử dụng Composer để quản lý một số package, có thể dùng **Git Submodule**:
```sh
git submodule add https://github.com/vendor/package.git packages/package
```
Sau đó, thêm autoload vào `composer.json`:
```json
"autoload": {
    "psr-4": {
        "Vendor\\Package\\": "packages/package/src/"
    }
}
```
Cập nhật autoload:
```sh
composer dump-autoload
```

---

## **8. Cấu Hình Advanced Trong `composer.json`**
### **Thiết lập phiên bản PHP yêu cầu**
Bạn có thể ép Composer kiểm tra phiên bản PHP:
```json
"config": {
    "platform": {
        "php": "8.1.0"
    }
}
```
Điều này giúp đảm bảo môi trường của bạn nhất quán.

### **Giới hạn số lượng package song song khi cài đặt**
Nếu bạn có mạng yếu, giới hạn số kết nối song song:
```sh
composer config process-timeout 600
composer config --global secure-http false
composer config --global http-basic.repo.packagist.com username password
```

---

## **9. Composer Audit – Kiểm Tra Bảo Mật**
Composer có thể kiểm tra lỗ hổng bảo mật trong package của bạn:
```sh
composer audit
```
Nếu có package dễ bị tấn công, bạn sẽ nhận được cảnh báo.

---

## **10. Kết Hợp Composer Với Docker**
Khi làm việc với Docker, bạn có thể tối ưu Composer bằng cách dùng `multi-stage build`:
```dockerfile
FROM composer:latest as builder
WORKDIR /app
COPY composer.json composer.lock /app/
RUN composer install --no-dev --optimize-autoloader

FROM php:8.1-fpm
COPY --from=builder /app /var/www/html
WORKDIR /var/www/html
```
Điều này giúp giảm dung lượng Docker image bằng cách chỉ copy `vendor/` mà không chứa các package dev.

---

## **Tóm Tắt**
✔️ **Tối ưu Composer** với `cache`, `performance optimization`, `parallel install`.  
✔️ **Sử dụng Private Repository** như Packagist Private, Satis, Git Submodule.  
✔️ **Tạo Plugin Composer** để mở rộng tính năng.  
✔️ **Debug Composer** với `composer diagnose`, `composer depends`.  
✔️ **Kết hợp Composer với Docker và CI/CD** để tăng tốc độ deploy.  
✔️ **Bảo mật dependency với `composer audit`**.  
