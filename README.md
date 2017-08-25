# gulp-Sass
关于对gulp自动化工具Sass的理解

安装gulp过程省略==

### 终端（terminal）：
#### 创建目录：
``` bash
mkdir 目录名
```
#### 进入目录：
``` bash
cd 目录名
```
#### 创建sass目录
``` bash
mkdir sass
```
#### 创建sass文件
``` bash
touch sass／index.scss
```
#### 创建gulpfiles.js
``` bash
touch gulpfiles.js     //创建gulpfiles可以在生成package.json后创建

npm init        //生成package.json,避免要手工生成
```
#### 安装依赖
``` bash
npm install --save-dev gulp gulp-sass gulp-autoprefixer    //三个模块
```

### IDE:
#### 打开gulpfile.js 编写gulp构建逻辑
``` bash
var gulp = require('gulp');
var sass = require('gulp-sass');
var autoprefixer = require('gulp-autoprefixer');

gulp.task('demo',function(){       //gulp.task()注册任务，第一个参数任务名称，第二个参数执行逻辑
  return gulp.src('sass/index.scss')
  .pipe(sass())
  .pipe(autoprefixer())  //pipe()模拟管道符操作方式
  .pipe(gulp.desk('css'));
})
```
#### 编写sass/index.scss
``` bash
.star{
    animation: .25s, 100ms;
}
```
### terminal:
``` bash
gulp demo
```
此时会发现项目中多了一个css文件夹，里面有一个index.css
``` bash
.star {
  -webkit-animation: .25s, 100ms;
          animation: .25s, 100ms; 
          }
 ```
 可见，gulp demo 已经自动完成了sass到css的编译，并添加了适当的浏览器前缀。
