- [**1. Kiến thức cơ bản về Laravel**](#1-kiến-thức-cơ-bản-về-laravel)
  - [**Laravel là gì? Tại sao bạn chọn Laravel thay vì các framework PHP khác?**](#laravel-là-gì-tại-sao-bạn-chọn-laravel-thay-vì-các-framework-php-khác)
  - [**Bạn hiểu gì về kiến trúc MVC trong Laravel? Laravel tuân theo mô hình nào?**](#bạn-hiểu-gì-về-kiến-trúc-mvc-trong-laravel-laravel-tuân-theo-mô-hình-nào)
  - [**Middleware trong Laravel là gì? Nó hoạt động như thế nào?**](#middleware-trong-laravel-là-gì-nó-hoạt-động-như-thế-nào)
  - [**Service Provider là gì? Khi nào cần tạo một Service Provider?**](#service-provider-là-gì-khi-nào-cần-tạo-một-service-provider)
  - [**Composer đóng vai trò gì trong Laravel?**](#composer-đóng-vai-trò-gì-trong-laravel)
- [**2. Routing và Controller**](#2-routing-và-controller)
  - [**Laravel xử lý route như thế nào?**](#laravel-xử-lý-route-như-thế-nào)
  - [**Bạn biết gì về route parameters? Phân biệt `Route::get('/user/{id}')` và `Route::get('/user/{id?}')`?**](#bạn-biết-gì-về-route-parameters-phân-biệt-routegetuserid-và-routegetuserid)
  - [**Middleware có thể được áp dụng vào route như thế nào?**](#middleware-có-thể-được-áp-dụng-vào-route-như-thế-nào)
- [**3. Eloquent ORM và Database**](#3-eloquent-orm-và-database)
  - [**Eloquent ORM là gì? Nó hoạt động như thế nào?**](#eloquent-orm-là-gì-nó-hoạt-động-như-thế-nào)
  - [**Soft delete là gì? Laravel hỗ trợ như thế nào?**](#soft-delete-là-gì-laravel-hỗ-trợ-như-thế-nào)
- [**4. Authentication \& Authorization**](#4-authentication--authorization)
  - [**Guard và Provider trong Laravel Auth là gì?**](#guard-và-provider-trong-laravel-auth-là-gì)
  - [**Khi nào sử dụng Policies và khi nào sử dụng Gates?**](#khi-nào-sử-dụng-policies-và-khi-nào-sử-dụng-gates)
- [**🔹 Policies và Gates trong Laravel**](#-policies-và-gates-trong-laravel)
  - [**1. Khái niệm**](#1-khái-niệm)
  - [**2. Khi nào nên dùng Gate và Policy?**](#2-khi-nào-nên-dùng-gate-và-policy)
  - [**3. Cách sử dụng Gate trong Laravel**](#3-cách-sử-dụng-gate-trong-laravel)
    - [**📌 Định nghĩa Gate**](#-định-nghĩa-gate)
    - [**📌 Kiểm tra quyền trong Controller hoặc Middleware**](#-kiểm-tra-quyền-trong-controller-hoặc-middleware)
  - [**4. Cách sử dụng Policy trong Laravel**](#4-cách-sử-dụng-policy-trong-laravel)
    - [**📌 Tạo Policy**](#-tạo-policy)
    - [**📌 Định nghĩa quyền trong Policy**](#-định-nghĩa-quyền-trong-policy)
    - [**📌 Đăng ký Policy trong `AuthServiceProvider.php`**](#-đăng-ký-policy-trong-authserviceproviderphp)
    - [**📌 Kiểm tra quyền trong Controller**](#-kiểm-tra-quyền-trong-controller)
- [**5. So sánh Gate và Policy**](#5-so-sánh-gate-và-policy)
- [**5. Caching, Queue, Event \& Job**](#5-caching-queue-event--job)
  - [**Laravel hỗ trợ những phương thức cache nào? Khi nào nên sử dụng cache?**](#laravel-hỗ-trợ-những-phương-thức-cache-nào-khi-nào-nên-sử-dụng-cache)
  - [**Queue trong Laravel là gì? Laravel hỗ trợ những loại queue nào?**](#queue-trong-laravel-là-gì-laravel-hỗ-trợ-những-loại-queue-nào)
- [**6. API Development \& Testing**](#6-api-development--testing)
  - [**Bạn đã từng tạo API bằng Laravel chưa? Bạn thường sử dụng công cụ nào để test API?**](#bạn-đã-từng-tạo-api-bằng-laravel-chưa-bạn-thường-sử-dụng-công-cụ-nào-để-test-api)
- [**7. Bảo mật và Best Practices**](#7-bảo-mật-và-best-practices)
  - [**Laravel có sẵn những tính năng bảo mật nào?**](#laravel-có-sẵn-những-tính-năng-bảo-mật-nào)
  - [**Làm thế nào để chống SQL Injection và XSS trong Laravel?**](#làm-thế-nào-để-chống-sql-injection-và-xss-trong-laravel)
  - [**Khi nào nên sử dụng `bcrypt()` và `Hash::make()` để mã hóa mật khẩu?**](#khi-nào-nên-sử-dụng-bcrypt-và-hashmake-để-mã-hóa-mật-khẩu)
- [**1. Service Container – Trái tim của Laravel** ❤️](#1-service-container--trái-tim-của-laravel-️)
  - [🔹 **Service Container là gì?**](#-service-container-là-gì)
  - [📌 **Ví dụ: Truyền dependency thủ công** (Cách cũ, không dùng Service Container)](#-ví-dụ-truyền-dependency-thủ-công-cách-cũ-không-dùng-service-container)
  - [📌 **Dùng Service Container (Dependency Injection)**](#-dùng-service-container-dependency-injection)
- [**2. Event \& Listener – Xử lý sự kiện không đồng bộ** 🔄](#2-event--listener--xử-lý-sự-kiện-không-đồng-bộ-)
  - [🔹 **Event \& Listener là gì?**](#-event--listener-là-gì)
  - [📌 **Ví dụ: Gửi email khi user đăng ký thành công**](#-ví-dụ-gửi-email-khi-user-đăng-ký-thành-công)
  - [**Bước 1: Tạo Event \& Listener**](#bước-1-tạo-event--listener)
  - [**Bước 2: Định nghĩa Event `UserRegistered.php`**](#bước-2-định-nghĩa-event-userregisteredphp)
  - [**Bước 3: Định nghĩa Listener `SendWelcomeEmail.php`**](#bước-3-định-nghĩa-listener-sendwelcomeemailphp)
  - [**Bước 4: Đăng ký Event \& Listener** (`EventServiceProvider.php`)](#bước-4-đăng-ký-event--listener-eventserviceproviderphp)
  - [**Bước 5: Gửi Event trong Controller**](#bước-5-gửi-event-trong-controller)
- [**3. Task Scheduling – Tự động hóa với Scheduler** ⏳](#3-task-scheduling--tự-động-hóa-với-scheduler-)
  - [🔹 **Task Scheduling là gì?**](#-task-scheduling-là-gì)
  - [**Bước 1: Định nghĩa Task trong `app/Console/Kernel.php`**](#bước-1-định-nghĩa-task-trong-appconsolekernelphp)
- [**4. API Resource – Tạo API chuẩn RESTful nhanh chóng** 🌍](#4-api-resource--tạo-api-chuẩn-restful-nhanh-chóng-)
  - [🔹 **API Resource là gì?**](#-api-resource-là-gì)
  - [**📌 Giải pháp: Dùng API Resource**](#-giải-pháp-dùng-api-resource)
  - [**Bước 1: Tạo Resource**](#bước-1-tạo-resource)
  - [**Bước 2: Định nghĩa API Resource**](#bước-2-định-nghĩa-api-resource)
  - [**Bước 3: Áp dụng Resource vào API**](#bước-3-áp-dụng-resource-vào-api)
- [**🎯 Kết luận**](#-kết-luận)
  - [**📌 Service Container và Service Provider trong Laravel – Giống và khác nhau?**](#-service-container-và-service-provider-trong-laravel--giống-và-khác-nhau)
- [**3️⃣ So sánh Service Container và Service Provider**](#3️⃣-so-sánh-service-container-và-service-provider)
- [🔥 **Sự khác nhau giữa `register()` và `boot()` trong Service Provider (Laravel)**](#-sự-khác-nhau-giữa-register-và-boot-trong-service-provider-laravel)
  - [**1️⃣ `register()` – Đăng ký service vào Service Container**](#1️⃣-register--đăng-ký-service-vào-service-container)
    - [🔹 Chức năng chính:](#-chức-năng-chính)
    - [📌 **Ví dụ: Đăng ký Service với `register()`**](#-ví-dụ-đăng-ký-service-với-register)
  - [**2️⃣ `boot()` – Chạy sau khi tất cả Service Provider đã đăng ký**](#2️⃣-boot--chạy-sau-khi-tất-cả-service-provider-đã-đăng-ký)
    - [🔹 Chức năng chính:](#-chức-năng-chính-1)
    - [📌 **Ví dụ: Đăng ký Event Listener trong `boot()`**](#-ví-dụ-đăng-ký-event-listener-trong-boot)
    - [**3️⃣ Khi nào dùng `register()` và `boot()`?**](#3️⃣-khi-nào-dùng-register-và-boot)
    - [**4️⃣ Ví dụ đầy đủ: Tạo Service Provider với cả `register()` và `boot()`**](#4️⃣-ví-dụ-đầy-đủ-tạo-service-provider-với-cả-register-và-boot)
    - [**🎯 Kết luận**](#-kết-luận-1)
- [Dưới đây là cách sử dụng chính xác các chức năng này trong `register()` và `boot()`.](#dưới-đây-là-cách-sử-dụng-chính-xác-các-chức-năng-này-trong-register-và-boot)
  - [**📌 1️⃣ Config (`config()`)**](#-1️⃣-config-config)
    - [🔹 **Dùng trong `register()`**](#-dùng-trong-register)
  - [**📌 2️⃣ View (`view()->composer()`, `view()->share()`)**](#-2️⃣-view-view-composer-view-share)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot)
  - [**📌 3️⃣ Component Blade (`Blade::component()`, `Blade::directive()`)**](#-3️⃣-component-blade-bladecomponent-bladedirective)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot-1)
  - [**📌 4️⃣ Route (`Route::middleware()`, `Route::prefix()`)**](#-4️⃣-route-routemiddleware-routeprefix)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot-2)
  - [**📌 5️⃣ Event \& Observer (`Event::listen()`, `Model::observe()`)**](#-5️⃣-event--observer-eventlisten-modelobserve)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot-3)
  - [**📌 6️⃣ Middleware (`app()->routeMiddleware()`)**](#-6️⃣-middleware-app-routemiddleware)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot-4)
  - [**📌 7️⃣ Macro (`Route::macro()`)**](#-7️⃣-macro-routemacro)
    - [🔹 **Dùng trong `boot()`**](#-dùng-trong-boot-5)
  - [**📌 Tổng kết: Cái nào nên đặt ở `register()` và `boot()`?**](#-tổng-kết-cái-nào-nên-đặt-ở-register-và-boot)


---

## **1. Kiến thức cơ bản về Laravel**  

### **Laravel là gì? Tại sao bạn chọn Laravel thay vì các framework PHP khác?**  
Laravel là một framework PHP mạnh mẽ, theo mô hình MVC, giúp phát triển web nhanh chóng, có cú pháp rõ ràng, dễ đọc và hỗ trợ nhiều tính năng tiện lợi như Eloquent ORM, Blade Template, Artisan CLI, Middleware, Queue, Events...  

🔥 **Lý do chọn Laravel:**  
- **Cộng đồng lớn, tài liệu phong phú** → Dễ học, dễ hỗ trợ.  
- **Cấu trúc rõ ràng** → Code dễ bảo trì.  
- **Tích hợp sẵn nhiều tính năng** → Authentication, Queue, Caching, API... không cần viết lại từ đầu.  
- **Eloquent ORM mạnh mẽ** → Quản lý database dễ dàng hơn nhiều so với Query thuần.  

---

### **Bạn hiểu gì về kiến trúc MVC trong Laravel? Laravel tuân theo mô hình nào?**  
Laravel tuân theo mô hình **MVC (Model - View - Controller)**:  
- **Model**: Quản lý dữ liệu, giao tiếp với database thông qua Eloquent ORM.  
- **View**: Hiển thị giao diện, thường sử dụng Blade Template.  
- **Controller**: Xử lý logic, nhận request từ route, gọi Model xử lý dữ liệu, trả về View hoặc JSON.  

🔥 **Lợi ích:** Giúp code gọn gàng, dễ bảo trì, dễ mở rộng.  

---

### **Middleware trong Laravel là gì? Nó hoạt động như thế nào?**  
Middleware là một lớp trung gian trong Laravel, dùng để xử lý request trước khi nó đến Controller.  

🔹 **Ví dụ:**  
- `auth` middleware kiểm tra user đã đăng nhập chưa.  
- `throttle` middleware giới hạn số request để tránh spam API.  

🔥 **Cách dùng:**  
- Đăng ký middleware trong `app/Http/Kernel.php`.  
- Áp dụng cho route:  
  ```php
  Route::get('/dashboard', [DashboardController::class, 'index'])->middleware('auth');
  ```  

---

### **Service Provider là gì? Khi nào cần tạo một Service Provider?**  
Service Provider trong Laravel là nơi đăng ký các dịch vụ của ứng dụng. Nó khởi tạo các class, binding vào service container, hoặc chạy bất kỳ logic khởi tạo nào.  

🔥 **Khi nào cần tạo Service Provider?**  
- Khi cần đăng ký một service dùng nhiều lần trong app (VD: custom helper, event listener).  
- Khi cần mở rộng functionality của Laravel (VD: thêm custom validation rule).  

📌 **Tạo Service Provider:**  
```bash
php artisan make:provider MyServiceProvider
```  
Sau đó đăng ký trong `config/app.php`.  

---

### **Composer đóng vai trò gì trong Laravel?**  
Composer là công cụ quản lý package của PHP. Laravel dùng Composer để cài đặt và quản lý thư viện bên thứ ba.  

🔥 **Ví dụ:** Cài đặt package Laravel UI  
```bash
composer require laravel/ui
```  

---

## **2. Routing và Controller**  

### **Laravel xử lý route như thế nào?**  
Laravel định nghĩa route trong file `routes/web.php` (cho web) hoặc `routes/api.php` (cho API). Khi có request, Laravel kiểm tra route tương ứng và gọi Controller hoặc Closure function.  

🔥 **Ví dụ:**  
```php
Route::get('/users', [UserController::class, 'index']);
```
Khi người dùng truy cập `/users`, Laravel gọi `UserController@index`.  

---

### **Bạn biết gì về route parameters? Phân biệt `Route::get('/user/{id}')` và `Route::get('/user/{id?}')`?**  
- `Route::get('/user/{id}')`: `id` là bắt buộc. Nếu không có, Laravel báo lỗi.  
- `Route::get('/user/{id?}')`: `id` là tùy chọn. Nếu không có, Laravel không báo lỗi.  

🔥 **Ví dụ:**  
```php
Route::get('/user/{id?}', function ($id = 1) {
    return "User ID: " . $id;
});
```

---

### **Middleware có thể được áp dụng vào route như thế nào?**  
Có 3 cách:  
1. **Dùng trực tiếp trong route**  
   ```php
   Route::get('/dashboard', [DashboardController::class, 'index'])->middleware('auth');
   ```
2. **Gán middleware trong Controller**  
   ```php
   class DashboardController extends Controller {
       public function __construct() {
           $this->middleware('auth');
       }
   }
   ```
3. **Gán trong nhóm route**  
   ```php
   Route::middleware(['auth', 'admin'])->group(function () {
       Route::get('/dashboard', [DashboardController::class, 'index']);
   });
   ```

---

## **3. Eloquent ORM và Database**  

### **Eloquent ORM là gì? Nó hoạt động như thế nào?**  
Eloquent ORM là hệ thống ORM (Object-Relational Mapping) của Laravel, giúp làm việc với database dễ dàng hơn bằng cách sử dụng model thay vì viết SQL trực tiếp.  

🔥 **Ví dụ:** Lấy tất cả user  
```php
$users = User::all();
```  
Thay vì SQL:  
```sql
SELECT * FROM users;
```

---

### **Soft delete là gì? Laravel hỗ trợ như thế nào?**  
Soft delete giúp xóa dữ liệu "ảo", tức là dữ liệu chỉ bị ẩn đi thay vì xóa khỏi database. Laravel hỗ trợ thông qua `deleted_at`.  

🔥 **Cách dùng:**  
1. Thêm `use SoftDeletes` vào model:  
   ```php
   use Illuminate\Database\Eloquent\SoftDeletes;

   class User extends Model {
       use SoftDeletes;
   }
   ```
2. Khi xóa:  
   ```php
   User::find(1)->delete(); // Chỉ cập nhật deleted_at, không xóa cứng
   ```
3. Khi lấy dữ liệu:  
   - `User::all();` → Không lấy user đã bị xóa.  
   - `User::withTrashed()->get();` → Lấy tất cả, kể cả user đã xóa.  

---

## **4. Authentication & Authorization**  

### **Guard và Provider trong Laravel Auth là gì?**  
- **Guard**: Xác định cách user được xác thực (session, token...).  
- **Provider**: Xác định nguồn dữ liệu user (database, API...).  

🔥 **Ví dụ:** Laravel mặc định dùng `users` table trong database. Nếu muốn dùng API token, ta có thể đổi guard sang `api`.  

---

### **Khi nào sử dụng Policies và khi nào sử dụng Gates?**  
- **Gate**: Dùng cho logic đơn giản, kiểm tra quyền trong file `AuthServiceProvider.php`.  
- **Policy**: Dùng cho quyền phức tạp, liên quan đến model cụ thể.  

🔥 **Ví dụ:**  
```php
Gate::define('edit-post', function ($user, $post) {
    return $user->id === $post->user_id;
});
```
 

---

## **🔹 Policies và Gates trong Laravel**  

### **1. Khái niệm**  
- **Gate**: Là một cơ chế đơn giản giúp kiểm tra quyền truy cập tại bất kỳ đâu trong ứng dụng.  
- **Policy**: Là một lớp chuyên dụng để quản lý quyền trên một model cụ thể.  

---

### **2. Khi nào nên dùng Gate và Policy?**  
| **Tiêu chí**          | **Gate** | **Policy** |
|----------------------|---------|-----------|
| Sử dụng cho...       | Logic đơn giản | Model cụ thể |
| Định nghĩa ở đâu?   | `AuthServiceProvider.php` | Một class riêng (`app/Policies/`) |
| Khi nào dùng?        | Kiểm tra nhanh quyền truy cập | Kiểm soát quyền chi tiết hơn |
| Ví dụ               | Xác định ai có thể truy cập trang Admin | Chỉ user tạo bài viết mới được chỉnh sửa bài viết đó |

---

### **3. Cách sử dụng Gate trong Laravel**  

#### **📌 Định nghĩa Gate**  
Khai báo trong `App\Providers\AuthServiceProvider.php`:  
```php
use Illuminate\Support\Facades\Gate;
use App\Models\User;
use App\Models\Post;

class AuthServiceProvider extends ServiceProvider {
    public function boot() {
        Gate::define('edit-post', function (User $user, Post $post) {
            return $user->id === $post->user_id;
        });
    }
}
```
Gate này kiểm tra xem user có quyền chỉnh sửa bài viết hay không (chỉ chủ bài viết mới có quyền).  

#### **📌 Kiểm tra quyền trong Controller hoặc Middleware**  
```php
if (Gate::allows('edit-post', $post)) {
    // Cho phép chỉnh sửa
}
```
Hoặc sử dụng `forbidden()` nếu không có quyền:  
```php
Gate::authorize('edit-post', $post);
```
Nếu user không có quyền, Laravel sẽ tự động trả về lỗi 403.  

---

### **4. Cách sử dụng Policy trong Laravel**  

#### **📌 Tạo Policy**  
Chạy lệnh Artisan:  
```bash
php artisan make:policy PostPolicy
```
Lệnh này tạo file `app/Policies/PostPolicy.php`.  

#### **📌 Định nghĩa quyền trong Policy**  
```php
namespace App\Policies;

use App\Models\User;
use App\Models\Post;

class PostPolicy {
    // Chỉ cho phép user sửa bài viết của chính họ
    public function update(User $user, Post $post) {
        return $user->id === $post->user_id;
    }
}
```

#### **📌 Đăng ký Policy trong `AuthServiceProvider.php`**  
```php
use App\Models\Post;
use App\Policies\PostPolicy;

protected $policies = [
    Post::class => PostPolicy::class,
];
```

#### **📌 Kiểm tra quyền trong Controller**  
```php
public function update(Request $request, Post $post) {
    $this->authorize('update', $post);

    // Nếu user có quyền, tiếp tục xử lý update
}
```
Nếu user không có quyền, Laravel tự động trả về lỗi **403 Forbidden**.  

🔥 **Lợi ích của Policy**  
- Dễ mở rộng, quản lý quyền chặt chẽ theo từng model.  
- Giúp Controller ngắn gọn, không bị lộn xộn với logic phân quyền.  

---

## **5. So sánh Gate và Policy**  

| **Tiêu chí**        | **Gate** | **Policy** |
|--------------------|---------|-----------|
| Mức độ phức tạp    | Đơn giản | Phức tạp hơn |
| Sử dụng cho model? | Không | Có |
| Định nghĩa quyền   | Trong `AuthServiceProvider.php` | Trong class riêng |
| Khi nào nên dùng?  | Kiểm tra quyền truy cập đơn giản, không liên quan đến model | Kiểm soát quyền chi tiết trên model |

🔹 **Tóm lại:**  
- Nếu cần kiểm tra quyền đơn giản, như "User có phải Admin không?" → **Dùng Gate**.  
- Nếu cần kiểm tra quyền với một Model (User chỉ có thể sửa bài viết của họ) → **Dùng Policy**.  


## **5. Caching, Queue, Event & Job**  

### **Laravel hỗ trợ những phương thức cache nào? Khi nào nên sử dụng cache?**  
Laravel hỗ trợ nhiều driver cache:  
- `file` → Mặc định, lưu cache vào file.  
- `database` → Lưu vào database.  
- `redis` / `memcached` → Hiệu suất cao, dùng cho hệ thống lớn.  

🔥 **Ví dụ:**  
```php
Cache::put('key', 'value', 60); // Lưu cache trong 60 phút
$value = Cache::get('key'); // Lấy cache
Cache::forget('key'); // Xóa cache
```

---

### **Queue trong Laravel là gì? Laravel hỗ trợ những loại queue nào?**  
Queue giúp xử lý công việc không đồng bộ, giảm tải cho server. Laravel hỗ trợ các driver:  
- `sync` → Chạy ngay lập tức.  
- `database` → Lưu queue vào database.  
- `redis` / `sqs` → Dùng cho hệ thống lớn.  

🔥 **Ví dụ:** Tạo job:  
```bash
php artisan make:job SendEmailJob
```
Trong `SendEmailJob.php`:  
```php
public function handle() {
    Mail::to($this->user->email)->send(new WelcomeMail());
}
```
Dispatch job:  
```php
dispatch(new SendEmailJob($user));
```
---

## **6. API Development & Testing**  

### **Bạn đã từng tạo API bằng Laravel chưa? Bạn thường sử dụng công cụ nào để test API?**  
- Laravel hỗ trợ API thông qua `routes/api.php`.  
- Công cụ test API phổ biến: **Postman**, **Insomnia**, **cURL**.  
- Laravel có thể dùng **Laravel Sanctum** hoặc **Laravel Passport** để tạo API authentication.  

🔥 **Ví dụ:** Tạo API Resource  
```php
Route::apiResource('posts', PostController::class);
```
---

## **7. Bảo mật và Best Practices**  

### **Laravel có sẵn những tính năng bảo mật nào?**  
- **CSRF Protection** → Laravel tự động thêm CSRF token vào form.  
- **XSS Protection** → Laravel escape đầu ra khi dùng `{!! $var !!}`.  
- **SQL Injection Protection** → Dùng Query Builder hoặc Eloquent thay vì query thuần.  

🔥 **Ví dụ:**  
```php
$users = DB::select("SELECT * FROM users WHERE email = '$email'"); // Không an toàn ❌
$users = DB::table('users')->where('email', $email)->get(); // An toàn ✅
```

---

### **Làm thế nào để chống SQL Injection và XSS trong Laravel?**  
- **Dùng Query Builder hoặc Eloquent thay vì raw SQL.**  
- **Escape dữ liệu đầu ra với `e()` hoặc Blade `{!! !!}`**  
- **Dùng Laravel Validation để kiểm tra input trước khi xử lý.**  

🔥 **Ví dụ về XSS Protection:**  
```php
{!! $user->name !!} // Không an toàn ❌
{{ $user->name }}   // An toàn ✅
```

---

### **Khi nào nên sử dụng `bcrypt()` và `Hash::make()` để mã hóa mật khẩu?**  
- Laravel khuyến nghị dùng `Hash::make()`, vì nó sử dụng bcrypt theo mặc định.  
```php
$password = Hash::make('password123');
```
- Không bao giờ lưu mật khẩu thuần vào database!  

---

Laravel có rất nhiều tính năng hay ho, nhưng tôi sẽ chọn những tính năng **mạnh mẽ, thực tế và hữu ích** nhất mà bạn nên biết để làm việc hiệu quả với Laravel.  

---

## **1. Service Container – Trái tim của Laravel** ❤️  

### 🔹 **Service Container là gì?**  
Service Container trong Laravel là một hệ thống **dependency injection (DI)** giúp quản lý các class và dependency của chúng một cách tự động.  

🔥 **Lợi ích:**  
✅ Tăng khả năng tái sử dụng code.  
✅ Hạn chế sự phụ thuộc cứng (hardcoded dependencies).  
✅ Dễ mở rộng và bảo trì.  

### 📌 **Ví dụ: Truyền dependency thủ công** (Cách cũ, không dùng Service Container)  
```php
class SMSService {
    public function send($message) {
        return "Sending SMS: $message";
    }
}

class UserNotification {
    protected $sms;

    public function __construct() {
        $this->sms = new SMSService(); // Hardcoded dependency ❌
    }

    public function notify($message) {
        return $this->sms->send($message);
    }
}
```
- **Vấn đề:** Chúng ta đang **gắn chặt** `UserNotification` với `SMSService`, nếu muốn đổi sang `EmailService`, ta phải sửa code.  

### 📌 **Dùng Service Container (Dependency Injection)**
```php
class UserNotification {
    protected $sms;

    public function __construct(SMSService $sms) {
        $this->sms = $sms; // Dependency Injection ✅
    }

    public function notify($message) {
        return $this->sms->send($message);
    }
}
```
Trong Laravel, **Service Container tự động tiêm dependency** mà không cần `new SMSService()`.  

📌 **Đăng ký Service trong Laravel**  
```php
app()->bind('SMSService', function () {
    return new SMSService();
});
```
Sau đó, gọi ở Controller:  
```php
$sms = app('SMSService'); 
echo $sms->send("Hello!");
```
🔥 **Kết quả:** Code linh hoạt hơn, dễ test, dễ mở rộng! 🚀  

---

## **2. Event & Listener – Xử lý sự kiện không đồng bộ** 🔄  

### 🔹 **Event & Listener là gì?**  
Laravel hỗ trợ **Event-Driven Architecture**, giúp tách biệt logic xử lý, tránh code quá tải trong Controller.  

📌 **Khi nào nên dùng?**  
✅ Khi cần gửi thông báo (email, SMS, push notification).  
✅ Khi cần log hành động của user.  
✅ Khi cần thực hiện tác vụ nền (background job).  

---

### 📌 **Ví dụ: Gửi email khi user đăng ký thành công**  

### **Bước 1: Tạo Event & Listener**  
```bash
php artisan make:event UserRegistered
php artisan make:listener SendWelcomeEmail
```

### **Bước 2: Định nghĩa Event `UserRegistered.php`**  
```php
namespace App\Events;
use App\Models\User;
use Illuminate\Foundation\Events\Dispatchable;
use Illuminate\Queue\SerializesModels;

class UserRegistered {
    use Dispatchable, SerializesModels;
    
    public $user;
    
    public function __construct(User $user) {
        $this->user = $user;
    }
}
```

### **Bước 3: Định nghĩa Listener `SendWelcomeEmail.php`**  
```php
namespace App\Listeners;
use App\Events\UserRegistered;
use Illuminate\Support\Facades\Mail;

class SendWelcomeEmail {
    public function handle(UserRegistered $event) {
        Mail::to($event->user->email)->send(new \App\Mail\WelcomeMail($event->user));
    }
}
```

### **Bước 4: Đăng ký Event & Listener** (`EventServiceProvider.php`)  
```php
protected $listen = [
    UserRegistered::class => [
        SendWelcomeEmail::class,
    ],
];
```

### **Bước 5: Gửi Event trong Controller**  
```php
use App\Events\UserRegistered;

public function register(Request $request) {
    $user = User::create($request->all());
    event(new UserRegistered($user)); // Kích hoạt Event
}
```
🔥 **Kết quả:** Khi user đăng ký, Laravel tự động gửi email mà Controller không cần lo về việc gửi mail! 😍  

---

## **3. Task Scheduling – Tự động hóa với Scheduler** ⏳  

### 🔹 **Task Scheduling là gì?**  
Thay vì dùng `cron job` truyền thống, Laravel có Task Scheduler để quản lý **công việc định kỳ** dễ dàng hơn.  

📌 **Ví dụ: Chạy một công việc mỗi ngày lúc 00:00**  

### **Bước 1: Định nghĩa Task trong `app/Console/Kernel.php`**  
```php
protected function schedule(Schedule $schedule) {
    $schedule->command('backup:run')->dailyAt('00:00');
}
```
🔥 **Kết quả:** Mỗi ngày lúc 00:00, Laravel tự động chạy lệnh `backup:run`.  

📌 **Chạy Scheduler trên server:**  
```bash
* * * * * php /path-to-your-project/artisan schedule:run >> /dev/null 2>&1
```
🔥 **Lợi ích:** Quản lý task định kỳ dễ dàng, không cần viết từng cron job riêng biệt! 🚀  

---

## **4. API Resource – Tạo API chuẩn RESTful nhanh chóng** 🌍  

### 🔹 **API Resource là gì?**  
Laravel có **Eloquent API Resource**, giúp trả về dữ liệu API đẹp hơn, dễ đọc hơn.  

📌 **Ví dụ: Trả về danh sách user**  
```php
Route::get('/users', function() {
    return User::all();
});
```
🔹 **Vấn đề:** **Không linh hoạt** → API trả về toàn bộ dữ liệu trong `users` table, bao gồm cả những trường không cần thiết (như `password`).  

---

### **📌 Giải pháp: Dùng API Resource**  

### **Bước 1: Tạo Resource**  
```bash
php artisan make:resource UserResource
```
Laravel tạo file: `app/Http/Resources/UserResource.php`  

### **Bước 2: Định nghĩa API Resource**  
```php
namespace App\Http\Resources;

use Illuminate\Http\Resources\Json\JsonResource;

class UserResource extends JsonResource {
    public function toArray($request) {
        return [
            'id' => $this->id,
            'name' => $this->name,
            'email' => $this->email,
            'created_at' => $this->created_at->format('Y-m-d'),
        ];
    }
}
```
🔥 **Lợi ích:** Không trả về **password**, chỉ trả về **các trường cần thiết**!  

### **Bước 3: Áp dụng Resource vào API**  
```php
Route::get('/users', function() {
    return UserResource::collection(User::all());
});
```
📌 **Kết quả:** API trả về dữ liệu **gọn gàng, chuẩn RESTful** 😍  

```json
[
    {
        "id": 1,
        "name": "John Doe",
        "email": "john@example.com",
        "created_at": "2025-02-08"
    }
]
```
🔥 **Lợi ích:**  
✅ Giúp API trả về dữ liệu đúng chuẩn, không bị dư thừa.  
✅ Dễ dàng tùy chỉnh định dạng dữ liệu.  
✅ Dùng được cả với **single resource** (`UserResource::make($user)`) và **collection** (`UserResource::collection($users)`).  

---

## **🎯 Kết luận**  

Trên đây là **4 tính năng mạnh mẽ** của Laravel giúp bạn code nhanh hơn, dễ bảo trì hơn:  
1️⃣ **Service Container** – Giúp quản lý dependency tốt hơn.  
2️⃣ **Event & Listener** – Giúp code gọn gàng, dễ mở rộng.  
3️⃣ **Task Scheduling** – Giúp tự động hóa công việc định kỳ.  
4️⃣ **API Resource** – Giúp API trả về dữ liệu đúng chuẩn.  

### **📌 Service Container và Service Provider trong Laravel – Giống và khác nhau?**  

💡 **Tóm tắt nhanh:**  
- **Service Container** 🛠️ → Là hệ thống **quản lý dependency (DI – Dependency Injection)** của Laravel.  
- **Service Provider** 📦 → Là nơi đăng ký các service vào **Service Container**.  

➡️ **Service Provider sử dụng Service Container để bind các service.**  

---

## **3️⃣ So sánh Service Container và Service Provider**  

| **Tiêu chí**           | **Service Container** 🛠️ | **Service Provider** 📦 |
|-----------------------|------------------|-----------------|
| **Là gì?** | Hệ thống Dependency Injection | Lớp đăng ký service vào container |
| **Chức năng chính** | Quản lý dependency, inject tự động | Đăng ký service, khởi tạo khi Laravel boot |
| **Dùng ở đâu?** | Toàn bộ ứng dụng Laravel | Trong `app/Providers/` |
| **Ví dụ sử dụng** | `app()->bind()`, `app()->make()` | `this->app->bind()`, `config/app.php` |
| **Khi nào nên dùng?** | Khi cần inject dependency vào Controller, Service | Khi cần khởi tạo nhiều service cùng lúc |

📌 **Tóm lại:**  
- **Service Container giúp quản lý và inject dependency** (giống một cái kho chứa service).  
- **Service Provider là nơi đăng ký các service vào Service Container** (giống một người quản lý kho).  

## 🔥 **Sự khác nhau giữa `register()` và `boot()` trong Service Provider (Laravel)**  

Khi làm việc với **Service Provider**, bạn sẽ thấy hai phương thức chính:  

- **`register()`** – Đăng ký service vào Service Container.  
- **`boot()`** – Khởi động service sau khi tất cả provider đã được đăng ký.  

Hiểu rõ sự khác biệt giữa hai phương thức này giúp bạn **quản lý service một cách tối ưu và tránh lỗi vòng lặp dependency**.

---

### **1️⃣ `register()` – Đăng ký service vào Service Container**
#### 🔹 Chức năng chính:
✔ **Dùng để bind các class, singleton vào Service Container**  
✔ **Chỉ đăng ký service mà không chạy logic liên quan đến ứng dụng**  
✔ **Chạy trước phương thức `boot()`**  
✔ **Không thể truy cập các service khác đã đăng ký trong `boot()`**

#### 📌 **Ví dụ: Đăng ký Service với `register()`**
```php
use App\Services\PaymentService;
use Illuminate\Support\ServiceProvider;

class PaymentServiceProvider extends ServiceProvider {
    public function register() {
        // Đăng ký service vào container
        $this->app->singleton(PaymentService::class, function ($app) {
            return new PaymentService();
        });
    }
}
```
🔹 **Tại sao lại đặt trong `register()`?**  
- Vì `register()` **chỉ thực hiện việc đăng ký**, không chạy bất kỳ logic nào.  
- Laravel đảm bảo tất cả các service được đăng ký trước khi ứng dụng khởi động.  

---

### **2️⃣ `boot()` – Chạy sau khi tất cả Service Provider đã đăng ký**
#### 🔹 Chức năng chính:
✔ **Chạy sau khi tất cả service đã được đăng ký**  
✔ **Có thể truy cập các service khác trong ứng dụng**  
✔ **Dùng để đăng ký Event, Observer, Middleware, Route, Blade directive,...**  

#### 📌 **Ví dụ: Đăng ký Event Listener trong `boot()`**
```php
use App\Events\OrderPlaced;
use App\Listeners\SendOrderNotification;
use Illuminate\Support\Facades\Event;

class PaymentServiceProvider extends ServiceProvider {
    public function boot() {
        Event::listen(OrderPlaced::class, SendOrderNotification::class);
    }
}
```
🔹 **Tại sao lại đặt trong `boot()`?**  
- Vì **sự kiện cần các service đã được đăng ký trước khi sử dụng**.  

---

#### **3️⃣ Khi nào dùng `register()` và `boot()`?**
| Chức năng | `register()` | `boot()` |
|-----------|------------|---------|
| Bind class vào Service Container | ✅ | ❌ |
| Bind singleton | ✅ | ❌ |
| Định nghĩa helper function | ✅ | ❌ |
| Đăng ký middleware | ❌ | ✅ |
| Đăng ký event listener | ❌ | ✅ |
| Đăng ký route, policy, observer | ❌ | ✅ |
| Tạo macro | ❌ | ✅ |
| Chạy các tác vụ khởi động (bootstrapping) | ❌ | ✅ |

---

#### **4️⃣ Ví dụ đầy đủ: Tạo Service Provider với cả `register()` và `boot()`**
```php
use App\Services\PaymentService;
use Illuminate\Support\ServiceProvider;
use Illuminate\Support\Facades\Event;
use App\Events\OrderPlaced;
use App\Listeners\SendOrderNotification;

class PaymentServiceProvider extends ServiceProvider {
    public function register() {
        // Đăng ký service vào Service Container
        $this->app->singleton(PaymentService::class, function ($app) {
            return new PaymentService();
        });
    }

    public function boot() {
        // Đăng ký sự kiện sau khi tất cả provider đã được đăng ký
        Event::listen(OrderPlaced::class, SendOrderNotification::class);
    }
}
```
✔ **Service được đăng ký trước (register)**, sau đó mới được sử dụng trong `boot()`.  

---

#### **🎯 Kết luận**
| Đặc điểm | `register()` | `boot()` |
|----------|------------|---------|
| Chạy trước hay sau? | **Trước** khi app khởi động | **Sau** khi tất cả service được đăng ký |
| Truy cập service khác? | ❌ Không thể | ✅ Có thể |
| Bind service vào container? | ✅ Có | ❌ Không |
| Đăng ký middleware, event, observer? | ❌ Không | ✅ Có |

Các hàm thiết lập **config, view, component, route,...** trong Laravel thường được sử dụng trong **Service Provider**, nhưng cần đặt chúng vào đúng phương thức (`register()` hoặc `boot()`) để tránh lỗi và tối ưu hiệu suất.  

## Dưới đây là cách sử dụng chính xác các chức năng này trong `register()` và `boot()`.  

### **📌 1️⃣ Config (`config()`)**
#### 🔹 **Dùng trong `register()`**
- Vì config cần được thiết lập **trước khi ứng dụng khởi chạy**, nên phải đặt trong `register()`.  
- Nếu cần **merge file config tùy chỉnh**, dùng `mergeConfigFrom()`.

📌 **Ví dụ: Thêm config vào Service Provider**  
```php
class AppServiceProvider extends ServiceProvider {
    public function register() {
        // Nạp file config tùy chỉnh
        $this->mergeConfigFrom(__DIR__.'/../config/custom.php', 'custom');
    }
}
```
📌 **Sử dụng trong ứng dụng**  
```php
$value = config('custom.key');
```
✔ **Lý do**: **Config cần được đăng ký trước khi app chạy**.

---

### **📌 2️⃣ View (`view()->composer()`, `view()->share()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì **view chỉ được load khi request chạy**, nên phải đặt trong `boot()`.  

📌 **Ví dụ: Chia sẻ biến cho tất cả view**  
```php
use Illuminate\Support\Facades\View;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        // Chia sẻ biến `appName` cho tất cả view
        View::share('appName', config('app.name'));
    }
}
```
📌 **Ví dụ: Sử dụng `view()->composer()` để truyền dữ liệu vào nhiều view**  
```php
use Illuminate\Support\Facades\View;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        View::composer(['home', 'dashboard'], function ($view) {
            $view->with('userCount', \App\Models\User::count());
        });
    }
}
```
✔ **Lý do**: **View chỉ hoạt động khi request chạy, nên không thể đặt trong `register()`**.

---

### **📌 3️⃣ Component Blade (`Blade::component()`, `Blade::directive()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì Blade component/directive **chỉ cần đăng ký khi chạy ứng dụng**, nên phải đặt trong `boot()`.  

📌 **Ví dụ: Đăng ký Blade Component**  
```php
use Illuminate\Support\Facades\Blade;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        // Đăng ký Blade component
        Blade::component('alert', \App\View\Components\Alert::class);
    }
}
```
📌 **Ví dụ: Đăng ký Blade Directive**  
```php
use Illuminate\Support\Facades\Blade;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        Blade::directive('datetime', function ($expression) {
            return "<?php echo (new DateTime($expression))->format('Y-m-d H:i'); ?>";
        });
    }
}
```
✔ **Lý do**: **Blade chỉ cần khi request chạy, nên không cần load sớm trong `register()`**.

---

### **📌 4️⃣ Route (`Route::middleware()`, `Route::prefix()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì **route cần middleware, prefix...** nên phải đặt trong `boot()`.  

📌 **Ví dụ: Load route từ file khác**  
```php
use Illuminate\Support\Facades\Route;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        $this->loadRoutesFrom(__DIR__.'/../routes/custom.php');
    }
}
```
📌 **Ví dụ: Định nghĩa middleware nhóm**  
```php
use Illuminate\Support\Facades\Route;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        Route::middleware(['auth'])->group(function () {
            Route::get('/dashboard', function () {
                return view('dashboard');
            });
        });
    }
}
```
✔ **Lý do**: **Route chỉ cần khi ứng dụng chạy, nên không cần load trong `register()`**.

---

### **📌 5️⃣ Event & Observer (`Event::listen()`, `Model::observe()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì các **Event & Observer** chỉ cần hoạt động khi request chạy, nên đặt trong `boot()`.  

📌 **Ví dụ: Đăng ký Observer**  
```php
use App\Models\User;
use App\Observers\UserObserver;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        User::observe(UserObserver::class);
    }
}
```
📌 **Ví dụ: Đăng ký Event Listener**  
```php
use Illuminate\Support\Facades\Event;
use App\Events\OrderPlaced;
use App\Listeners\SendOrderNotification;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        Event::listen(OrderPlaced::class, SendOrderNotification::class);
    }
}
```
✔ **Lý do**: **Event & Observer không cần load sớm, chỉ cần khi request chạy**.

---

### **📌 6️⃣ Middleware (`app()->routeMiddleware()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì Middleware chỉ cần khi ứng dụng chạy, nên đặt trong `boot()`.  

📌 **Ví dụ: Đăng ký Middleware tùy chỉnh**  
```php
use Illuminate\Contracts\Http\Kernel;
use App\Http\Middleware\CheckAge;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        $this->app['router']->aliasMiddleware('check.age', CheckAge::class);
    }
}
```
✔ **Lý do**: **Middleware chỉ dùng khi request chạy, nên đặt trong `boot()`**.

---

### **📌 7️⃣ Macro (`Route::macro()`)**
#### 🔹 **Dùng trong `boot()`**
- Vì Macro chỉ cần khi ứng dụng chạy, nên đặt trong `boot()`.  

📌 **Ví dụ: Tạo macro cho route**  
```php
use Illuminate\Support\Facades\Route;

class AppServiceProvider extends ServiceProvider {
    public function boot() {
        Route::macro('admin', function ($prefix, $callback) {
            Route::prefix($prefix)->middleware('admin')->group($callback);
        });
    }
}
```
✔ **Lý do**: **Macro chỉ cần khi route chạy, không cần load sớm**.

---

### **📌 Tổng kết: Cái nào nên đặt ở `register()` và `boot()`?**
| Chức năng | `register()` | `boot()` |
|-----------|------------|---------|
| Merge config | ✅ | ❌ |
| Bind service vào container | ✅ | ❌ |
| Đăng ký middleware | ❌ | ✅ |
| Đăng ký route | ❌ | ✅ |
| Đăng ký Blade component | ❌ | ✅ |
| Đăng ký Blade directive | ❌ | ✅ |
| Đăng ký View composer/share | ❌ | ✅ |
| Đăng ký Event listener | ❌ | ✅ |
| Đăng ký Observer | ❌ | ✅ |
| Đăng ký Macro | ❌ | ✅ |

---
