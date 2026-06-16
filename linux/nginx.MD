# nginx 配置

## install

```bash
sudo apt update && sudo apt install -y nginx

nginx -v

systemctl status nginx --no-pager # 查看状态

sudo systemctl enable --now nginx #开机自启
```

## uninstall
```bash
# 1) 停止并禁用服务
sudo systemctl stop nginx nginx.service nginx.socket 2>/dev/null || true
sudo systemctl disable nginx nginx.service nginx.socket 2>/dev/null || true
sudo systemctl daemon-reload

# 2) 卸载主包 + 常见子包
sudo apt purge -y 'nginx*' 'libnginx*'

# 3) 自动清理无用依赖与缓存
sudo apt autoremove -y --purge
sudo apt autoclean

# 4) 删除残留目录（谨慎：会删配置/日志/缓存）
sudo rm -rf /etc/nginx /var/log/nginx /var/lib/nginx /var/cache/nginx

# 5) 删除可能遗留的 systemd drop-in（若存在）
sudo rm -rf /etc/systemd/system/nginx.service.d /etc/systemd/system/nginx.service
sudo systemctl daemon-reload
sudo systemctl reset-failed

# 6) 验证
dpkg -l | grep -E 'nginx|libnginx' || true
systemctl status nginx --no-pager || true
which nginx || true
```

## start
```bash
# 1) 语法检查（非常重要）
sudo nginx -t

# 2) 平滑重载（不中断已有连接）
sudo systemctl reload nginx

sudo systemctl restart nginx
```