---
layout: post
title: ScodeScanner v2.0.0
---

ScodeScanner is an automated tool, created in purpose of finding the vulnerabilities inside the source code before commiting it into the production. This will help the developers to quickly identify the vulnerabilities and patch those vulnerabilities at Dev Time. 

### In Support Language

ScodeScanner only supports PHP for now, but soon it will start supporting other languages too. 

### Whats new?

1) This new version supports semgrep.<br>
2) Better code which is easy to understand.<br>
3) Capability of finding difficult patterned vulnerabilities.<br>

### Scanned 1k+ files

I scanned 1k+ files from different php open source code and it was observed that SQL Injection was the most of the common vulnerability that was identified, the second one is Cross-Site Scripting issues, where developers free used user untrusted input inside the code.

Here is the sample data - 

```
uploads/PHP-Multi-Cloud-School-Management-/application/models/Parents_model.php 
     temp.Rule-SQLi-$school_id
        Possible SQL Injection for variable -  $school_id


        171┆  ... $school_id."' AND status='paid';"; ... [0m
[Shortened a long line from output, adjust with --max-chars-per-line]
          ⋮┆----------------------------------------
        180┆  ... $school_id."' AND status='paid';"; ... [0m
[Shortened a long line from output, adjust with --max-chars-per-line]
          ⋮┆----------------------------------------
        189┆  ... $school_id."';"; ... [0m
[Shortened a long line from output, adjust with --max-chars-per-line]
          ⋮┆----------------------------------------
        198┆ $myquery = "SELECT * FROM students_payment WHERE session = '".$session."' AND student_id ='".$child['student_id']."' AND school_id='".$school_id."';";


 uploads/PHP-Multi-Cloud-School-Management-/application/views/public/contact_view.php 
     temp.Rule-XSS-$_SESSION["action_status_report"]
        XSS Injection -- $_SESSION["action_status_report"]


         18┆ echo $_SESSION['action_status_report'];
          ⋮┆----------------------------------------
     temp.Rule-XSS-$_SESSION['action_status_report']
        XSS Injection -- $_SESSION['action_status_report']


         18┆ echo $_SESSION['action_status_report'];


 uploads/PHP-Multi-Cloud-School-Management-/application/views/public/login_view.php 
     temp.Rule-XSS-$_SESSION['err_msg']
        XSS Injection -- $_SESSION['err_msg']


         14┆ echo $_SESSION['err_msg'];


 uploads/PHP-Multi-Cloud-School-Management-/application/views/public/pre_payment_gateway_view.php 
     temp.Rule-XSS-$ref
        XSS Injection -- $ref


         52┆ echo $ref;


 uploads/PHP-Multi-Cloud-School-Management-/system/libraries/Cache/drivers/Cache_redis.php 
     temp.Rule-unserialize-$value
        Found unserialize Injection for variable -  $value


        158┆ return unserialize($value);


 uploads/complete-php7-ecom-website/addtowishlist.php 
     temp.Rule-XSS-$pid
        XSS Injection -- $pid


         42┆ echo $sql = "INSERT INTO `wishlist` (`pid`, `uid`) VALUES ('$pid', '$uid')";
          ⋮┆----------------------------------------
     temp.Rule-XSS-$uid
        XSS Injection -- $uid


         42┆ echo $sql = "INSERT INTO `wishlist` (`pid`, `uid`) VALUES ('$pid', '$uid')";


 uploads/complete-php7-ecom-website/admin/delcategory.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


         10┆ $sql = "DELETE FROM category WHERE id='$id'";


 uploads/complete-php7-ecom-website/admin/delprodimg.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


         10┆ $sql = "SELECT thumb FROM products WHERE id=$id";


 uploads/complete-php7-ecom-website/admin/delproduct.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


         10┆ $sql = "SELECT thumb FROM products WHERE id=$id";


 uploads/complete-php7-ecom-website/admin/editcategory.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


         42┆ $sql = "SELECT * FROM category WHERE id=$id";
          ⋮┆----------------------------------------
     temp.Rule-XSS-$_GET['id']
        XSS Injection -- $_GET['id']


         46┆ <input type="hidden" name="id" value="<?php echo $_GET['id']; ?>">


 uploads/complete-php7-ecom-website/admin/editproduct.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


         70┆ $sql = "SELECT * FROM products WHERE id=$id";


 uploads/complete-php7-ecom-website/admin/login.php 
     temp.Rule-SQLi-$password
        Possible SQL Injection for variable -  $password


         34┆ $sql = "SELECT * FROM `admin` WHERE `email`='$email' AND `password`='$password'";


 uploads/complete-php7-ecom-website/admin/order-process.php 
     temp.Rule-SQLi-$oid
        Possible SQL Injection for variable -  $oid


         64┆ $ordsql = "SELECT * FROM orders WHERE id='$oid'";
          ⋮┆----------------------------------------
     temp.Rule-XSS-$_GET['id']
        XSS Injection -- $_GET['id']


        103┆ <input type="hidden" name="orderid" value="<?php echo $_GET['id']; ?>">
          ⋮┆----------------------------------------
     temp.Rule-XSS-$id
        XSS Injection -- $id


         21┆ echo $ordprcsql = "INSERT INTO ordertracking (orderid, status, message) VALUES ('$id', '$status', '$message')";


 uploads/complete-php7-ecom-website/cancel-order.php 
     temp.Rule-SQLi-$oid
        Possible SQL Injection for variable -  $oid


        104┆ $ordsql = "SELECT * FROM orders WHERE id='$oid'";
          ⋮┆----------------------------------------
     temp.Rule-SQLi-$uid
        Possible SQL Injection for variable -  $uid


         66┆ $sql = "SELECT * FROM usersmeta WHERE uid=$uid";
          ⋮┆----------------------------------------
     temp.Rule-XSS-$_GET['id']
        XSS Injection -- $_GET['id']


        137┆ <input type="hidden" name="orderid" value="<?php echo $_GET['id']; ?>">


 uploads/complete-php7-ecom-website/checkout.php 
     temp.Rule-SQLi-$uid
        Possible SQL Injection for variable -  $uid


         50┆ $userSql = "SELECT * FROM `usersmeta` WHERE `uid`='$uid'";


 uploads/complete-php7-ecom-website/delwishlist.php 
     temp.Rule-XSS-$id
        XSS Injection -- $id


         41┆ echo $sql = "DELETE FROM wishlist WHERE id=$id";


 uploads/complete-php7-ecom-website/inc/nav.php 
     temp.Rule-XSS-$cart
        XSS Injection -- $cart


         42┆ echo "<em>" . count($cart) . "</em>";


 uploads/complete-php7-ecom-website/single.php 
     temp.Rule-SQLi-$id
        Possible SQL Injection for variable -  $id


        195┆ $chkrevsql = "SELECT count(*) `reviewcount` FROM `reviews` `r` WHERE r.uid='$uid' AND r.pid='$id'";
          ⋮┆----------------------------------------
     temp.Rule-SQLi-$uid
        Possible SQL Injection for variable -  $uid


        195┆ $chkrevsql = "SELECT count(*) `reviewcount` FROM `reviews` `r` WHERE r.uid='$uid' AND r.pid='$id'";


 uploads/complete-php7-ecom-website/view-order.php 
     temp.Rule-XSS-$oid
        XSS Injection -- $oid


         76┆ <h2>Order #<?php echo $oid; ?></h2>


 uploads/complete-php7-ecom-website/wishlist.php 
     temp.Rule-SQLi-$uid
        Possible SQL Injection for variable -  $uid


         75┆ $wishsql = "SELECT p.name, p.price, p.id AS pid, w.id AS id, w.`timestamp` FROM wishlist w JOIN products p WHERE w.pid=p.id AND w.uid='$uid'";

```

### Download

SCodeScanner hosted with GitHub. Head to the <a href="https://github.com/agrawalsmart7/scodescanner">GitHub repository</a> for downloads, bug reports, and features requests.

### Contribution

Would love your thoughts on this, and would be great to work with community.

Thanks!
