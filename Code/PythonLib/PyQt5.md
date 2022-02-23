# PyQt5 安装与配置

## 安装

- 在线安装

  ```python
  pip install PyQt5 -i https://pypi.douban.com/simple
  pip install pyqt5-tools -i https://pypi.douban.com/simple
  ```

- 离线安装

  - 不带Designer版

  ```python
  # 提前下载所需安装包
  pip download PyQt5 -i https://pypi.douban.com/simple
      
  # requirements.txt 大致内容
  PyQt5_Qt5-5.15.2-py3-none-win_amd64.whl
  PyQt5_sip-12.9.1-cp38-cp38-win_amd64.whl
  PyQt5-5.15.6-cp36-abi3-win_amd64.whl
  
  # 批量安装离线包
  pip install --no-index -r .\requirements.txt
  ```

  - 带Designer版

  ```python
  # 提前安装下载所需安装包
  pip download PyQt5 -i https://pypi.douban.com/simple
  pip download pyqt5-tools -i https://pypi.douban.com/simple
  
  # 处理包的版本冲突(尽量跟随Designer的伴随包)
  #	如果没有冲突就直接安装
  
  # requirements.txt 大致内容
  PyQt5_Qt5-5.15.2-py3-none-win_amd64.whl
  PyQt5_sip-12.9.1-cp38-cp38-win_amd64.whl
  pyqt5_tools-5.15.4.3.2-py3-none-any.whl
  pyqt5-5.15.4-cp36.cp37.cp38.cp39-none-win_amd64.whl
  pyqt5_plugins-5.15.4.2.2-cp38-cp38-win_amd64.whl
  python_dotenv-0.19.2-py2.py3-none-any.whl
  qt5_tools-5.15.2.1.2-py3-none-any.whl
  click-7.1.2-py2.py3-none-any.whl
  qt5_applications-5.15.2.2.2-py3-none-win_amd64.whl
  
  # 批量安装离线包
  pip install --no-index -r .\requirements.txt
  ```

## 配置

- step1

  安装好后可以 `win` 搜索 `designer` 查看是否安装成功

- step2

  打开PyCharm，打开File—>Settings—>External Tools,点击加号来添加自己的工具

  ```python
  Name:QtDesigner
  Group:Qt
  Programs:F:\anaconda\Library\bin\designer.exe(这里是各位自己的designer路径，之前所看到的)
  Working directory：$ProjectFileDir$
  ```

- step3

  但是要在PyCharm中把界面的.ui文件转换为.py文件还需要后面的配置。

  重复上述操作，配置pyuic：

  ```python
  Name:Pyuic
  Group:Qt
  Program:F:\anaconda\python.exe(各位自己的python路径)
  Arguments：-m PyQt5.uic.pyuic $FileName$ -o $FileNameWithoutExtension$.py
  Working directory：$FileDir$
  ```

## 测试

回到PyCharm，Tools—>Qt—>QtDesigner，点击即可打开designer：

然后创建一个最简单的界面，把这个界面保存（默认是保存在当前pycharm项目目录下，我这里命名“first.ui”）

回到pycharm，可以看到工程目录下已经产生了first.ui，右键它，Qt—>Pyuic，点击后即可产生first.py文件，OK接下来就可以愉快地写代码了(⊙o⊙)…

# PyQt5_Tutorial

## PyQt5.QtWidgets

`PyQt5.QtWidgets` 模块包含了基本的组件。

### QApplication

每个PyQt5应用都必须创建一个应用对象

```python
import sys
from PyQt5.QtWidgets import QApplication
# sys.argv是一组命令行参数的列表。Python可以在shell里运行，这个参数提供对脚本控制的功能
app = QApplication(sys.argv)
# 当调用exit()方法或直接销毁主控件时，主循环就会结束。sys.exit()方法能确保主循环安全退出。外部环境能通知主控件怎么结束。
sys.exit(app.exec_())
```

### QWidget

- 创建对象

  ```python
  from PyQt5.QtWidgets import QWidget
  
  # 直接创建
  w = QWidget()
  
  # 用对象继承
  class Example(QWidget):
      def __init__(self):
          super().__init__()
          self.initUI()
  
      def initUI(self):
          # 使用继承自QWidget类的方法
          self.setGeometry(300, 300, 300, 220)
          self.setWindowTitle('Icon')
          self.setWindowIcon(QIcon('..\\..\\image\\Globe.ico'))
          self.show()
  ```

#### .close()

```python
close(self) -> bool		# 退出组件
```

#### .closeEvent()

```python
# 控件关闭时触发结束事件
closeEvent(self, QCloseEvent)

# 示例：
def closeEvent(self, event):
    # 第一个字符串显示在消息框的标题栏，第二个字符串显示在对话框，第三个参数是消息框的俩按钮，
    # 最后一个参数是默认按钮，这个按钮是默认选中的。返回值在变量reply里。
    reply = QMessageBox.question(self, 'Message', "Are you sure to quit?",
                                 QMessageBox.Yes | QMessageBox.No,
                                 QMessageBox.No)
    if reply == QMessageBox.Yes:
        event.accept()
    else:
        event.ignore()
```

#### .mouseMoveEvent()

```python
mouseMoveEvent(self, QMouseEvent)
```

#### .frameGeometry()

```python
# 得到了窗口的大小
frameGeometry(self) -> QRect
```

#### .resize()

```python
# 改变控件的大小
resize(self, QSize)
resize(self, int, int)		# 宽 和 高
```

#### .move()

```python
# 修改控件位置，注意屏幕的原点在左上角
move(self, QPoint)
move(self, int, int)
```

#### .setWindowTitle()

```python
# 窗口添加标题
setWindowTitle(self, str)
```

#### .show()

```python
# 让控件在桌面上显示出来,一般在类设置好后，最后调用显示
show(self)
```

#### .setGeometry()

```python
# setGeometry()有两个作用：把窗口放到屏幕上并且设置窗口大小。
# int x, int y, int w, int h	
setGeometry(self, QRect)
setGeometry(self, int, int, int, int)
```

#### .setWindowIcon()

```python
# 窗口左上角设置图标，参数为 QIcon 对象
setWindowIcon(self, QIcon)
```

#### .setToolTip()

```python
# 创建提示框可以使用富文本格式的内容。
setToolTip(self, str)

# 示例：
self.setToolTip('This is a <b>QWidget</b> widget')
```

#### .setLayout()

```python
setLayout(self, QLayout)
```

#### .setMouseTracking()	

```python
setMouseTracking(self, bool)
```

#### .sizeHint()

```python
# 提供一个默认的按钮大小
sizeHint(self) -> QSize
```

#### .QKeyEvent()

```python
keyPressEvent(self, QKeyEvent)

# 示例：
def keyPressEvent(self, e):
    if e.key() == Qt.Key_Escape:
        self.close()
```

### QAbstractButton

```python
class QAbstractButton(QWidget):
```

### QPushButton

```python
# text参数是想要显示的按钮名称，parent参数是放在按钮上的组件
class QPushButton(QAbstractButton):
# 示例：
QPushButton(parent: QWidget = None)
QPushButton(str, parent: QWidget = None)
QPushButton(QIcon, str, parent: QWidget = None)
```

#### .resize()

```python
# 改变控件的大小
resize(self, QSize)
resize(self, int, int)		# 宽 和 高
```

#### .move()

```python
# 修改控件位置，注意屏幕的原点在左上角
move(self, QPoint)
move(self, int, int)
```

#### .setToolTip()

```python
# 创建提示框可以使用富文本格式的内容。
setToolTip(self, str)

# 示例:
btn.setToolTip('This is a <b>QPushButton</b> widget')
```

#### .sizeHint()

```python
# 提供一个默认的按钮大小
sizeHint(self) -> QSize
```

### QDesktopWidget

```python
class QDesktopWidget(QWidget):
```

#### .availableGeometry()

```python
availableGeometry(self, screen: int = -1) -> QRect		# 获取显示器的分辨率
availableGeometry(self, QWidget) -> QRect
availableGeometry(self, QPoint) -> QRect
```

### QToolTip

#### .setFont

```python
# 静态方法;设置提示框的字体
setFont(QFont)

# 示例：
# 设置为10px的SansSerif字体
QToolTip.setFont(QFont('SansSerif', 10))
```

### QMessageBox

#### .question()

```python
# 第一个字符串显示在消息框的标题栏，第二个字符串显示在对话框，第三个参数是消息框的俩按钮，
# 最后一个参数是默认按钮，这个按钮是默认选中的。返回值在变量reply里。
question(QWidget, str, str, 
         buttons: Union[QMessageBox.StandardButtons, QMessageBox.StandardButton] = QMessageBox.StandardButtons(QMessageBox.Yes|QMessageBox.No), 
         defaultButton: QMessageBox.StandardButton = QMessageBox.NoButton) 
		-> QMessageBox.StandardButton
    
# 示例：
reply = QMessageBox.question(self, 'Message', "Are you sure to quit?",
                             QMessageBox.Yes | QMessageBox.No,
                             QMessageBox.No)
```

### QMainWindow

`QMainWindow`提供了主窗口的功能，使用它能创建一些简单的状态栏、工具栏和菜单栏。

```python
class QMainWindow(QWidget):
```

#### .statusBar()

```python
statusBar(self) -> QStatusBar		# 返回一个状态栏对象,同时开启状态栏显示
```

#### .menuBar()

```python
menuBar(self) -> QMenuBar		# 返回一个菜单栏对象
```

#### .contextMenuEvent()

```python
contextMenuEvent(self, QContextMenuEvent)		# 右键菜单的函数重载
```

#### .setCentralWidget()

```python
setCentralWidget(self, QWidget)		# 放在QMainWindow的中间区域。这个组件或占满所有剩余的区域。
```

### QStatusBar

```python
# 状态栏对象
class QStatusBar(QWidget):
```

#### .addToolBar()

```python
# 增加工具栏
addToolBar(self, Qt.ToolBarArea, QToolBar)
addToolBar(self, QToolBar)
addToolBar(self, str) -> QToolBar
```

#### .showMessage()

```python
showMessage(self, str, msecs: int = 0)		# 状态栏显示信息
```

#### .addMenu()

```python
addMenu(self, QMenu) -> QAction
addMenu(self, str) -> QMenu
addMenu(self, QIcon, str) -> QMenu
```

### QMenuBar

```python
# 菜单栏对象
class QMenuBar(QWidget):
```

#### .addAction()

```python
addAction(self, QAction)
addAction(self, str) -> QAction
addAction(self, QIcon, str) -> QAction
addAction(self, str, PYQT_SLOT, shortcut: Union[QKeySequence, QKeySequence.StandardKey, str, int] = 0) -> QAction
addAction(self, QIcon, str, PYQT_SLOT, shortcut: Union[QKeySequence, QKeySequence.StandardKey, str, int] = 0) -> QAction
```

### QMenu

```python
# 菜单对象
class QMenu(QWidget):

QMenu(parent: QWidget = None)
QMenu(str, parent: QWidget = None)
```

#### .addAction()

```python
addAction(self, QAction)
addAction(self, str) -> QAction
addAction(self, QIcon, str) -> QAction
addAction(self, str, PYQT_SLOT, shortcut: Union[QKeySequence, QKeySequence.StandardKey, str, int] = 0) -> QAction
addAction(self, QIcon, str, PYQT_SLOT, shortcut: Union[QKeySequence, QKeySequence.StandardKey, str, int] = 0) -> QAction
```

#### .addMenu()

```python
addMenu(self, QMenu) -> QAction
addMenu(self, str) -> QMenu
addMenu(self, QIcon, str) -> QMenu
```

### QToolBar

```python
class QToolBar(QWidget):

QToolBar(str, parent: QWidget = None)
QToolBar(parent: QWidget = None)
```

#### .addAction()

```python
addAction(self, QAction)
addAction(self, str) -> QAction
addAction(self, QIcon, str) -> QAction
addAction(self, str, PYQT_SLOT) -> QAction
addAction(self, QIcon, str, PYQT_SLOT) -> QAction
```

### QTextEdit

```python
class QTextEdit(QAbstractScrollArea):

QTextEdit(parent: QWidget = None)
QTextEdit(str, parent: QWidget = None)
```

### QLabel

```python
class QLabel(QFrame):

QLabel(parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags())
QLabel(str, parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags())
```

#### .move()

```python
# 修改控件位置，位置相对于父类而不是屏幕
move(self, QPoint)
move(self, int, int)
```

#### .setText()

```python
setText(self, str) 
```

### QLineEdit

```python
class QLineEdit(QWidget):
    """
    QLineEdit(parent: QWidget = None)
    QLineEdit(str, parent: QWidget = None)
    """
```

### QLCDNumber

```python
class QLCDNumber(QFrame):
    """
    QLCDNumber(parent: QWidget = None)
    QLCDNumber(int, parent: QWidget = None)
    """
```

#### .display()

```python
display(self, str)
display(self, float)
display(self, in	t)
```

### QAbstractSlider

```python
class QAbstractSlider(QWidget):
    """ QAbstractSlider(parent: QWidget = None) """
```

#### .valueChanged()

```python
valueChanged(self, int) [signal]
```

### QSlider

```python
class QSlider(QAbstractSlider):
    """
    QSlider(parent: QWidget = None)
    QSlider(Qt.Orientation, parent: QWidget = None)
    """
```

#### .valueChanged()

```python
valueChanged(self, int) [signal]
```

## QtCore

`from PyQt5.QtWidgets import QName`

### QAction

`from PyQt5.QtWidgets import QAction`

`QAction`是菜单栏、工具栏或者快捷键的动作的组合

```python
class QAction(__PyQt5_QtCore.QObject):
    
QAction(parent: QObject = None)
QAction(str, parent: QObject = None)
QAction(QIcon, str, parent: QObject = None)

# 示例：
viewStatAct = QAction('View statusbar', self, checkable=True)  # checkable 可选中的对象
```

#### .setShortcut()

```python
# 设置快捷键
setShortcut(self, Union[QKeySequence, QKeySequence.StandardKey, str, int])

# 示例：
setShortcut('Ctrl+Q')
```

#### .setStatusTip()

```python
setStatusTip(self, str)		# 设置状态栏显示
```

#### .setCheckable()

```python
setCheckable(self, bool)		# 设置是否为可选中的对象
```

#### .setChecked()

```python
setChecked(self, bool)		# 设置默认选中状态
```

#### .triggered()

```python
triggered(self, checked: bool = False) [signal]		# 触发一个信号

# 示例：
exitAct.triggered.connect(qApp.quit)
```

## QLayout

`from PyQt5.QtWidgets import QName`

```python
class QLayout(__PyQt5_QtCore.QObject, QLayoutItem):
    """
    QLayout(QWidget)
    QLayout()
    """
    
class QBoxLayout(QLayout):
    """ QBoxLayout(QBoxLayout.Direction, parent: QWidget = None) """
```

### QBoxLayout

```python
class QBoxLayout(QLayout):
    """ QBoxLayout(QBoxLayout.Direction, parent: QWidget = None) """
```

#### .addLayout()

```python
addLayout(self, QLayout, stretch: int = 0)
```

### QHBoxLayout

```python
class QHBoxLayout(QBoxLayout):
    
QHBoxLayout()
QHBoxLayout(QWidget)
```

### QGridLayout

```python
class QGridLayout(QLayout):
    @typing.overload
    def __init__(self, parent: QWidget) -> None: ...
    @typing.overload
    def __init__(self) -> None: ...
```

#### .addWidget()

```python
def addWidget(self, w: QWidget) -> None: ...
def addWidget(self, a0: QWidget, row: int, column: int, alignment: typing.Union[QtCore.Qt.Alignment, QtCore.Qt.AlignmentFlag] = ...) -> None: ...
def addWidget(self, a0: QWidget, row: int, column: int, rowSpan: int, columnSpan: int, alignment: typing.Union[QtCore.Qt.Alignment, QtCore.Qt.AlignmentFlag] = ...) -> None: ...
```

#### .addStretch()

```python
addStretch(self, stretch: int = 0)	# 在布局器中增加一个伸缩量，将nLayout的布局器的空白空间平均分配
```

#### .setSpacing()

```python
# 各个控件之间的上下间距
def setSpacing(self, spacing: int) -> None: ...
```

## __sip.simplewrapper

### QRect

```python
class QRect(__sip.simplewrapper):

QRect()
QRect(int, int, int, int)	# topLeft.x, topLeft.y, bottomRight.x, bottomRight.y 
QRect(QPoint, QPoint)		# 左上, 右下
QRect(QPoint, QSize)
QRect(QRect)
```

#### 基础调用

```python
adjust(self, int, int, int, int)		# ？
adjusted(self, int, int, int, int) -> QRect		# ？
bottom(self) -> int				# 返回控件的长
height(self) -> int				# 返回控件的高
bottomLeft(self) -> QPoint		# 返回左下点
bottomRight(self) -> QPoint		# 返回右下点
topLeft(self) -> QPoint			# 返回左上点
topRight(self) -> QPoint		# 返回右上点
center(self) -> QPoint			# 返回中心点
moveCenter(self, QPoint)		# 将中心点移动到QPoint
```

### QPoint

```python
class QPoint(__sip.simplewrapper):

QPoint()
QPoint(int, int)
QPoint(QPoint)
```

#### 基础调用

```python
x(self)
y(self)
setX(self, int)
setY(self, int)
dotProduct(QPoint, QPoint) -> int		# ?
manhattanLength(self) -> int			# 曼哈顿长度？
transposed(self) -> QPoint				# x,y 互换
```

## PyQt5.QtCore

### QCoreApplication

