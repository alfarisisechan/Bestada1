# Bestada
Bestada Test Nomer 1 (SQL)

- Buatlah query untuk menampilkan semua customer yang berasal dari kota Jakarta
> SELECT * FROM customers WHERE address = 'Jakarta';

- Buatlah query untuk menampilkan semua informasi pembelian yang sudah terkirim dari seluruh customer (mencangkup seluruh informasi pada ketiga table dan harus readable)
> SELECT * FROM shipments INNER JOIN orders ON shipments.order_id = orders.id INNER JOIN customers ON orders.customer_id = customers.id WHERE shipments.status = 'sent';

- Buatlah query untuk menampilkan jumlah pengiriman gagal dan pengiriman berhasil semua customer yang berasal dari kota Bekasi dari bulan Januari 2022 sampai bulan April 2022.
> SELECT COUNT(CASE WHEN shipments.status = 'cancle' THEN status END) AS gagal, COUNT(CASE WHEN shipments.status = 'sent' THEN status END) AS berhasil FROM shipments INNER JOIN orders ON shipments.order_id = orders.id INNER JOIN customers ON orders.customer_id = customers.id WHERE customers.address = 'Bekasi' AND shipments.create_at BETWEEN '2022/01/01' AND '2022/04/30';
