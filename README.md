<?php
// Viết một chương trình PHP để kiểm tra xem một số nguyên dương nào đó có phải số nguyên tố hay không. 
//Yêu cầu: Tạo một hàm isPrime nhận một số nguyên dương và trả về true nếu nó là số nguyên tố, ngược lại trả về false.
//Sử dụng hàm để hiển thị danh sách các số nguyên tố từ 1 đến 100.
function isPrime($num) {
    if($num < 2) {
        return false;
    }
    for($i = 2; $i <= sqrt($num); $i++) {
        if($num % $i == 0) {
            return false;
        }
    }
    return true;
}
for($i = 1; $i <= 100; $i++) {
    if(isPrime($i)) {
        echo $i . " ";
    }
}
echo "<br>";
//Bài 2: Viết một ứng dụng PHP để quản lý thông tin về sản phẩm trong một cửa hàng su dụng mảng kết hợp. 
//Yêu cầu: Tạo một mảng kết hợp chứa thông tin về sản phẩm với các khóa như name, price,và quantity. Hiển thị thông tin của tất cả sản phẩm trong mảng.
//Viết hàm để tính tổng giá trị của tất cả sản phẩm (price * quantity).
$products = [
    [
        "name" => "IPhone 15 ProMax",
        "price" => 39990000,
        "quantity" => 10,
    ],
    [
        "name" => "Samsung Galaxy S23 Ultra",
        "price" => 29990000,
        "quantity" => 20,
    ],
    [
        "name" => "MacBook Pro M2",
        "price" => 49990000,
        "quantity" => 15,
    ],
];
//Thông tin của tất cả sản phẩm trong mảng
foreach ($products as $product) {
    echo "Tên sản phẩm: " . $product["name"] . "<br>";
    echo "Giá sản phẩm: " . $product["price"] . "<br>";
    echo "Số lượng sản phẩm: " . $product["quantity"] . "<br>";
}
//Hàm để tính tổng giá trị của tất cả sản phẩm
function calculateTotalValue($products) {
    $totalValue = 0;
    foreach ($products as $product) {
        $totalValue += $product["price"] * $product["quantity"];
    }
    return $totalValue;
}
//Tổng giá trị của tất cả sản phẩm
$totalValue = calculateTotalValue($products);
echo "Tổng giá trị của tất cả sản phẩm: " . $totalValue . "<br>";
?>
