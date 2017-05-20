# NotePad
This is an AndroidStudio rebuild of google SDK sample NotePad<br>
## 实现了2个基本功能：<br>
1.显示Note的时间戳<br>
2.实现Note的搜索功能<br>
## 2个扩展功能:<br>
1.美化UI<br>
2.更改Note的背景<br>
<br>
<br>
## 首先实现时间戳功能需要进行修改的地方有，映射到数据库的PROJECTTION,绑定数据列的dataclolumn，还有绑定的ViewId，然后再listItem.xml文件添加时间戳的TEXTVIEW。修改时间戳的格式需要在NoteEditor的UpdateNote中进行修改。<br>
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/1.png?raw=true)
<br>
<br>
## 然后要实现搜索功能，我是通过创建一个新的Activity，再其layout中加入listview控件。在NoteList的optionmenu添加一条新的Item，创建点击事件通过intent跳到NoteSearch这个新的Activity中，然后再设置searchview的监听事件，重写onQueryTextChange方法来实现搜索。通过匹配对应的title和time完成搜索<br>
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/2.png?raw=true)
<br>
<br>
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/3.png?raw=true)
<br>
<br>
## 更改NoteEditor的背景通过添加optionmenu的item，创建点击事件，点击后打开一个Alertdialog，通过XML文件来配置Alertdialog。然后再上面的各种颜色TextView控件在添加点击事件实现更改Note背景，并把颜色数据保存到sharedpreference。在NoteEditor的Oncreate调用sharedpreference的数据来更改背景。同时返回到主界面也会更改相对应的背景。主界面的背景更换主要是从sharedpreference提取数据，然后重写NoteList的OnResume方法，获取sharedpreference的数据并刷新数据。<br>
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/4.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/5.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/6.png?raw=true)
<br>
<br>

## 美化UI主要是定义一个shape.xml文件，来设置每个Item的样式设计。如圆角边框和空间摆放。下面图片则对应的是不同颜色对应的不同主界面主题。
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/7.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/8.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/9.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/10.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/11.png?raw=true)
![Alt Text](https://github.com/chenlong1232014/NotePad/blob/master/app/src/main/res/image/12.png?raw=true)





