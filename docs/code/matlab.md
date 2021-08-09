## 散点图

``` matlab
A = xlsread('C:\...','sheet1');%读取Excel数据至Matlab Workspace中
X1= a(:,2);
Y1= a(:,3);
Z1= a(:,4);
scatter(X1,Y1,'k');  //二维散点图
scatter3(X1,Y1,Z1,'k');  //三维散点图
hold on;%将数据保持
xlabel('x'),ylabel('y'),zlabel('z');

% 'fill'  实心点

```

## 折线图

MATLAB对曲线的线型和颜色有许多选择，标注的方法是在每一对数组后加一个字符串参数，说明如下：   
线型（线方式）： -实线  :点线  -.虚点线  - -波折线。   
线型（点方式）： .圆点  +加号  *星号  x叉形  o小圆   
颜色： y黄  r红  g绿  b蓝  w白  k黑  m紫  c青

``` matlab
% 网格和标记 在一个图形上可以加网格、标题、x轴标记、y轴标记，用下列命令完成这些工作。 
>> x=linspace(0,2*pi,30); y=sin(x); z=cos(x); 
>> plot(x,y,x,z) 
>> grid%网格 
>> xlabel(‘Independent Variable X’)%x轴标记 
>> ylabel(‘Dependent Variables Y and Z’)%y轴标记 
>> title(‘Sine and Cosine Curves’)%标题
% 也可以在图形的任何位置加上一个字符串，如用：
>> text(2.5,0.7,’sinx’)  % 表示在坐标x=2.5, y=0.7处加上字符串sinx。
>> gtext(‘sinx’)  % 更方便的是用鼠标来确定字符串的位置，方法是输入命令在图形窗口十字线的交点是字符串的位置，用鼠标点一下就可以将字符串放在那里。
```


坐标系的控制  
在缺省情况下MATLAB自动选择图形的横、纵坐标的比例，如果你对这个比例不满意，可以用axis命令控制。  
axis([xmin xmax ymin ymax]) [ ]中分别给出x轴和y轴的最大值、最小值  
axis([0 6 0 1])  
axis equal 或 axis(‘equal’)  x轴和y轴的单位长度相同  
axis square 或 axis(‘square’) 图框呈方形
axis off 或 axis(‘off’) 清除坐标刻度



``` matlab
多幅图形 可以在同一个画面上建立几个坐标系, 用subplot(m,n,p)命令；把一个画面分成m×n个图形区域, p代表当前的区域号，在每个区域中分别画一个图,如 
>> x=linspace(0,2*pi,30); y=sin(x); z=cos(x); 
>> u=2*sin(x).*cos(x); v=sin(x)./cos(x); 
>> subplot(2,2,1),plot(x,y),axis([0 2*pi –1 1]),title(‘sin(x)’) >> subplot(2,2,2),plot(x,z),axis([0 2*pi –1 1]),title(‘cos(x)’) >> subplot(2,2,3),plot(x,u),axis([0 2*pi –1 1]),title(‘2sin(x)cos(x)’) >> subplot(2,2,4),plot(x,v),axis([0 2*pi –20 20]),title(‘sin(x)/cos(x)’)

```


图注
``` matlab
legend
```


``` matlab

```

## 根轨迹
``` matlab
num=[1,60];                             %开环传函分子多项式系数
den=conv([1,0],[1,6,9]); %开环传函分母多项式系数
sys=tf(num,den);                         %系统传递函数模型
rlocus(sys);                             %绘制系统的根轨迹图
axis([-8 2 -6 6]);                       %设定坐标范围为：实轴[-8,2]，虚轴[-6,6]
```

## 图片导出
策略 1：Figure  View -> 右键Copy  
策略 2：Figure  File -> Export Setup:Figure -> Properties；Figure  File -> Save As... -> '*.emf'  '*.tif'  '*.eps'  
策略 3：见下面代码
``` matlab
hfig = figure
figWidth = 5;  % 设置图片宽度
figHeight = 5;  % 设置图片高度
set(hfig,'PaperUnits','inches'); % 图片尺寸所用单位
set(hfig,'PaperPosition',[0 0 figWidth figHeight]);
fileout = ['test1.']; % 输出图片的文件名
print(hfig,[fileout,'tif'],'-r600','-dtiff'); % 设置图片格式、分辨率

```


``` matlab

```