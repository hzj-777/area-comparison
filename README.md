# 中国省级行政区面积比较 - 部署说明

## 项目文件

部署到 GitHub Pages 时，请确保以下两个文件在同一目录：

1. **index.html** - 主页面文件
2. **china.json** - 中国地图 GeoJSON 数据文件

## 部署步骤

### 1. 上传文件到 GitHub 仓库

将以下文件上传到你的 GitHub 仓库：
- index.html
- china.json

### 2. 启用 GitHub Pages

1. 进入仓库的 Settings（设置）
2. 找到 Pages 选项
3. 在 "Source" 下选择分支（通常是 main 或 master）
4. 保存设置

### 3. 访问网站

几分钟后，你的网站将在以下地址可用：
```
https://你的用户名.github.io/仓库名称/
```

## 问题排查

### 地图无法加载

如果看到 "加载地图失败" 错误：

1. **检查文件路径**：确保 china.json 和 index.html 在同一目录
2. **检查文件名**：确保文件名完全正确（区分大小写）
3. **等待部署完成**：GitHub Pages 部署可能需要几分钟
4. **清空浏览器缓存**：按 Ctrl+Shift+R (Windows) 或 Cmd+Shift+R (Mac) 强制刷新

### CORS 问题已解决

之前从阿里云 API 加载地图数据会遇到 CORS 限制。现在使用本地 JSON 文件，已经解决这个问题。

## 本地测试

如果想在本地测试，需要启动一个本地服务器：

### 使用 Python
```bash
# Python 3
python -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000
```

### 使用 Node.js
```bash
npx http-server
```

然后访问 `http://localhost:8000`

## 功能说明

- **查看模式**：点击地图查看单个省份面积
- **比较模式**：点击"开始面积比较"按钮，选择最多3个省份进行比较
- **全国排名**：点击"全国排名彩蛋"查看所有34个省级行政区的面积排名
