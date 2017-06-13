ucloud ufile storage for laravel
base on https://docs.ucloud.cn/api/ufile-api/index

config/filesystems.php
```php
    'disks' => [
        'ufile' => [
            'driver'  => 'ucloud-ufile',
            'bucket' => env('UFILE_BUCKET'),
            'suffix' => env('UFILE_SUFFIX'),
            'public_key'=> env('UFILE_ACCESS_KEY'),  //AccessKey
            'secret_key'=> env('UFILE_SECRET_KEY'),  //SecretKey
        ]
    ],
```
demo
```php
Storage::disk('ufile')->put('file.name', $file);
$url = Storage::disk('ufile')->url('file.name');
```
