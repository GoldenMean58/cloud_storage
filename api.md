# 用户部分

## 注册

`method`: `POST`

`path`: `/user/register`

`args`:

`username`: 用户名

`password`: 密码

`return valule`:

```json
{
	"code": 0,
	"msg": "Register successfully"
}
```

## 登录

`method`: `POST`

`path`: `/user/login`

`args`:

`username`: 用户名

`password`: 密码

`return valule`:

```json
{
	"code": 0,
	"msg": "Login successfully"
}
```

## 登出

`method`: `POST`

`path`: `/user/logout`

`return valule`:

```json
{
	"code": 0,
	"msg": "Logout successfully"
}
```

# 文件部分

## 查看

`method`: `POST`

`path`: `/files/view`

`args`:

`path`: 绝对路径(根目录/)，可以是文件或文件夹，或者`用户名+绝对路径`，如:`username/`, `username/test.jpg`

`user`: 用户名

`key`: 分享码(可选)

## 建立文件夹

`method`: `POST`

`path`: `/files/create_dir`

`args`:

`current_dir`: 当前文件夹的绝对路径(根目录/)

`dir_name`: 要创建的文件夹名


## 上传文件

`method`: `POST`

`path`: `/files/upload`

`args`:

`current_dir`: 当前文件夹的绝对路径(根目录/)

`file`: 文件

## 下载文件

`method`: `POST`

`path`: `/files/get_download`

`args`:

`user`: 用户名

`path`: 文件的绝对路径

`key`: 分享码(可选)

`return value`:

```json
{
	"code": 0,
	"link": xxx
}
```

`method`: `GET`

`path`: `/files/download/xxx/` xxx为上面获得的`link`,下载链接有有效期,过期需要重新获取

## 删除文件/文件夹

`method`: `POST`

`path`: `/files/delete`

`args`:

`current_dir`: 当前所在文件夹路径

`file_name`: 要删除的文件或文件夹名

## 移动文件/文件夹

`method`: `POST`

`path`: `/files/move`

`args`:

`src_path`: 源绝对路径

`dest_path`: 目的绝对路径

`/$recycle_bin$`是回收站的路径

## 恢复文件/文件夹

`method`: `POST`

`path`: `/files/restore`

`args`:

`path`: 要恢复的文件/文件夹的绝对路径(通常是回收站中的文件/文件夹的绝对路径路径)

## 复制文件/文件夹

`method`: `POST`

`path`: `/files/copy`

`args`:

`src_user`: 源用户

`src_path`: 源绝对路径

`dest_user`: 目标用户

`dest_path`: 目的绝对路径

`key`: 如果源用户与目标用户不一致则填写分享码，否则不需要填

## 分享

`method`: `POST`

`path`: `/files/share`

`args`:

`current_dir`: 当前所在文件夹的绝对路径

`file_name`: 要分享的文件/文件夹名

`key`: 分享码

`day`: 分享过期天数

## 取消分享

`method`: `POST`

`path`: `/files/unshare`

`args`:

`current_dir`: 当前所在文件夹的绝对路径

`file_name`: 文件/文件夹名

## 获取总空间大小

`method`: `POST`

`path`: `/files/get_total_size`

`Return value`:

```json
{
    "code": 0,
    "total_size": 1073741824 // 总可用字节(Byte)数
}
```

## 获取已使用空间大小

`method`: `POST`

`path`: `/files/get_used_size`

`Return value`:

```json
{
    "code": 0,
    "used_size": 0 // 已使用空间字节(Byte)数
}
```

## 获取空间使用情况

`method`: `POST`

`path`: `/files/get_space_size`

`Return value`:

```json
{
    "code": 0,
    "used_size": 0, // 已使用空间字节(Byte)数
    "total_size": 1024 // 总可用字节
}
```
