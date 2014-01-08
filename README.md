<pre>
*****************************************************
*                                                   *
*    中国日历类（Chinese Calendar Class (CCC)）     *
*                                                   *
*    作者： neweroica                               *
*                                                   *
*                                                   *
*    献给为自由代码而孜孜不倦工作的人们             *
*                                                   *
*                                                   *
* -- Simple is beauty                               *
*                                                   *
*                               2003年5月8日        *
*                                                   *
*****************************************************



一、关于中国日历类及版权申明

  1.版权申明

  #########################################################################

                    版权申明
  _______________________________________________________________________

  中国日历类（Chinese Calendar Class (CCC)）
  版本：v0.1，JavaScript版本

  版权所有 (C) 2002-2003 neweroica (wy25@mail.bnu.edu.cn)
  
  联系方式： Email:  wy25@mail.bnu.edu.cn

             QQ: 32460746

  本自由代码（JavaScript版本）遵照GPL标准和Open Source之精神，原则上免费为全世界任何编程人员
  使用、修改、重写成其他编程语言和重新发布，但希望您在进行以上行为时，出于对本代码原创发起者
  的艰辛劳动的尊重与肯定，敬请保留这段简短的版权信息，谢谢！
  ________________________________________________________________________


  ##########################################################################


  2.关于中国日历类（CCC-v0.1-js）

  很多年前，还在上中学的时候，我就开始对天文和历法感兴趣，既佩服西洋历法之简捷精准，又尝惊叹中国传统农历之巧妙，尤其是无中气置闰法。在中国传统文化的魅力和西方现代科学的双重影响下，我便开始试着将中国农历，干支，节气等等公式化，要知道古人往往用口诀代替公式，如推月干支、时干支的口诀，这不容易记忆，也不能反映出道理来。现在看来，这些早期的工作竟然使我能够在E时代借助于电脑和网络来实现万年历。

差不多前年（2002年）的这个时候，我刚刚开始自学做网页，学完HTML后又对脚本语言JavaScript感兴趣，于是自己边学边动手按照自己的意图编写程序，开始时每次出错都让自己焦躁不安，但每次成功也都使我激动不已。就这样，我在动手实践中（这相当重要），我逐渐熟练了JavaScript编程，甚至能编写较大型的程序了，如那年10月假期期间我独立的编写出俄罗斯方块游戏，虽然我已经发现网上还有更优秀的脚本，但对于什么都没有参考的我来说，算是很有成就感了。

我早就想编一个万年历的程序放在网上，前年刚学完JavaScript是曾编了一个的，凑合能用，但算法麻烦，每一年的农历信息需要17个数来确定，另外节气计算公式也有点错误。后来，我偶然在网上发现了由台湾的林洵贤先生编写的（后来由大陆的梅竹松修正）经典的200年JavaScript万年历，大大小小的网站许多都用了林先生的年历（但有的竟没说明版权），当时十分叹服。觉得自己和别人毕竟差了好大一截。终于在去年4月-5月，我利用课余时间花了一个多月的时间自己写了一个功能比较齐全的万年历，适用年数近三千年，除了阴历和阳历之外，还有儒略日、年代纪元、干支、日月食、节气交节时刻、黄道星座、各种节日（包括九九、三伏、梅雨）、人体生物钟、倒计时以及日记等功能，算法与林先生的截然不同，并且功能与准确度也是非林先生的万年历所能及的，如正规历书上记载1985年春分是3月21日，这与本年历计算结果完全一致，而林先生的万年历则给出是3月20日，其原因是我的算法考虑了岁差与章动，而林先生的则是用平节气的简单算法。

当时我把这个万年历叫做“知来者”，取自《周易·说卦传》孔子所说的“数往者顺，知来者逆”。刚做完不久，我就在北京大学未名BBS的网页设计（HomePage）板公开了全部源代码及相关注释。不少网友试用了“知来者”，给予我大力支持和鼓励，同时也提出了一些问题和建议，主要是速度较慢、个别农历日期有误以及界面可以再美化一些。然而其时我已没更多时间和精力了，所以也就一直拖了下去。

直到最近（整整一年之后），也就是在北京的这个“非典时期”，学校暂时停课，我才得以有时间重新修正我的万年历，不但纠正了原有的错误，而且又增加了一些功能，如历种的转化、甲子纳音、二十八星宿、世界时区等，增添了节日。然而，最为重要的是，我产生了构建“中国日历类”的想法。也就是说，我将我已经做好的所有关于中国日历的函数全部封装在一个叫做“中国日历类”（Chinese Calendar Class，简称CCC）里，这样，以后别人在需要用到有关中国日历的某种函数时（如求某年某月某日的农历日期，或是求几月几号有什么节日等等），就不必自己动手去编写代码了，而直接从CCC中取出来就行了，其容易程度就象是从光盘盒中取光/盘一样简单。

终于，又花了几天功夫，我终于基本实现了CCC的构建，并利用它重新写了一个在线万年历，不但纠正了以前的几处错误、增加了一些功能，而且速度和界面都有了改观。

最后，应当感谢曾次亮先生和Erling Poulsen，曾先生几十年的辛苦劳动使我得以将他的节气计算方法公式化，而我的朔望交食程序则是在Erling Poulsen的程序上加以简化和应用的。另外，波波网友细心地指出了1901-2050年个别农历日期的错误，在此也表示感谢。


二、中国日历类JavaScript版本（CCC-v0.1-js）的使用方法

  1.所包含的源代码文件

    所有源文件都在ccc0.1目录下，包括ccc.js, math.js, solar.js, sterm.js, ganzhi.js, lunar.js, string.js, ftvl.js, era.js和timezone.js。

    注意：在引用时，ccc0.1目录必须与引用的文件在同一目录下，并且不能更改ccc目录名。比如，C:\mypages目录下的calendar.htm要引用CCC，则可以将ccc目录放到C:\mypages下，并在源文件中加入：
    <script language="JavaScript" src="ccc0.1/ccc.js"></script>
   即可。

  2.新建一个CCC对象

    直接用new方法新建一个CCC对象，即

    var cccObject=new CCC(year,month,date,time,zone,calType);

    其中

    year（年）=正负整数，（ 0是公元前1年，-1是公元前2年等等）
    month（月）=1 -12
    date（日）=正负整数
    time=形如"22:30:15"（表示22时30分15秒）的字符串
    zone（世界时区）= -12 - +13 （负表示西时区，正表示东时区）
    calType（历种）=1,2,3 分别代表Normal（标准公历）,Gregorian（格里历）,Julian（儒略历）

    也可以采用较少的参数新建对象：

    三参数  var cccObject=new CCC(year,month,date)

    四参数  var cccObject=new CCC(year,month,date,time)

    四参数  var cccObject=new CCC(year,month,date,calType)

    五参数  var cccObject=new CCC(year,month,date,time,calType)

    六参数  var cccObject=new CCC(year,month,date,time,zone,calType)

    其中time,zone和calType的缺省值是"0:0:0",8和1。

    示例：

    var myCal=new CCC(2003,5,8,"14:19:50",8,1);

  3.CCC对象的方法

  出于代码执行速度的考虑，CCC对象没有采用属性而只赋予方法，因为在JavaScript中一旦新建一个对象,就必须同时初始化其所有属性，而这是一件不太明智的事情，因为当我们只想取得CCC的某一两个属性时，没有必要将它的所有其他属性都一一初始化一遍。因而我决定将所有CCC的一些性质都用相应的方法来取得。

  到目前为止，这些性质和方法分成三组（同样是出于代码执行速度的考虑）：

  1) CCC对象下的直接的方法

    语法是： cccObject.methodName()

    如： myCal.day()返回myCal对象的星期数

    CCC-v0.1-js的直接的方法如下：

    方法                                                    返回值

    year()                                                  年份数
    month()                                                 月份数
    date()                                                  日期数
    time()                                                  时间字符串
    hour()                                                  小时数
    minute()                                                分钟数
    second()                                                秒数
    zone()                                                  世界时区数
    calType()                                               日历类型数
    calType_Str()                                           日历类型字符串
    JulianDay()                                             儒略日
    day()                                                   星期数
    day_Str()                                               星期字符串（汉语）
    day_ENStr()                                             星期字符串（英语）
    solarZodiac()                                           十二星座数
    solarZodiac_Str()                                       十二星座字符串
    yGz()                                                   年干支数
    yGz_Str()                                               年干支字符串
    mGz()                                                   月干支数
    mGz_Str()                                               月干支字符串
    dGz()                                                   日干支数
    dGz_Str()                                               日干支字符串
    hGz()                                                   时干支数
    hGz_Str()                                               时干支字符串
    chineseZodiacName()                                     生肖字符串
    chineseEra()                                            年代纪元字符串
    stars28()                                               二十八宿数
    stars28_Str()                                           二十八宿字符串
    sFtvl()                                                 公历节日字符串
    jqFtvl()                                                节气节日字符串
    monthLength()                                           阳历本月长度（天数）
    monthLength_Str()                                       阳历本月长度（月大月小字符串）

  2) CCC对象的节气子类的方法

    首先建立CCC对象的节气子类对象： 

    var sTerm=cccObject.solarTerm();

    节气子类对象的属性（注意不是方法！）有两个：

    sTermInMonth  —— 一个字符串数组，包含所在阳历月的两个节气日期和交节时刻
    sTermName     —— 当前日期的节气名，若当天不是节气日，则是空字符串 
    sTermTime     —— 当前日期的节气交节时刻，若当天不是节气日，则是空字符串 

   示例：
    如：sTerm.sTermInMonth[0]
    
   3) CCC对象的农历子类的方法

    首先建立CCC对象的农历子类对象： 

    var myLunarCal=cccObject.lunar();

    农历子类对象的属性（注意不是方法！）有：

    属性                                                  值

    lunarDate                                             农历日期数
    lunarDate_Str                                         农历日期字符串
    lunarMonth                                            农历月份数
    lunarMonth_Str                                        农历月份字符串
    syzygyType                                            朔望类型数
    syzygyTime                                            朔望时刻（单位：天）
    syzygyTime_Str                                        朔望时刻（字符串
    syzygyName                                            朔望名称字符串
    ecliType                                              日月食类型数
    ecliType_Str                                          日月食类型字符串
    ecliTime                                              日月食发生时刻（单位：天）
    ecliTime_Str                                          日月食发生时刻（字符串）

   示例：
    如：myLunarCal.lunarDate_Str

三、进一步说明

  1.公历（西历）

    按照习惯，公元1582年10月4日之前（包括10月4日），采用儒略（Julian）历，公元1582年10月15日之后（包括10月15日），采用格里（Gregorian）历，公元1582年10月5日到10月14日，是格里历中被删掉的十天，故本年历无此十天。

  2.农历

    现行农历采用的是夏历（即建寅为正），所以本年历主要采用夏历，但由于历史上改朝换代或君王改换纪元等原因，曾有多次修改月建，在本年历中未作特别说明，现说明如下：
  i)公元前256年（秦襄昭王52年）采用秦历，此前一直采用古周历（但春秋战国时各国历法不一，较为混乱）。秦历以十月为岁首，“后九月”为闰月。
  ii)公元前105年，西汉太初元年五月改历，以正月为岁首，该年有十五个月（从十月、十一月、十二月、一月、二月、......十二月）。
  iii)公元9年，新朝王莽始建国1年，以12月为正月（丑月），故上一年无“十二月”。
  iv)公元23年，淮阳王改元更始，复用因寅正，以地皇十一月为更始1年的十月，故是年有两个十月。
  v)三国魏青龙5年（公元237年）三月，改元景初，建丑为正，以三月为四月，四月为五月，...，十二月为正月。而景初三年十二月，魏复寅正，故是年有两个十二月。
  vi)周武则天天授一年（载初1年，公元689年）十一月，该行周历子正。以十一月为岁首，该为载初1年正月，故乙丑年只有十个月。
  vii)久视1年十月复寅正，以正月为十一月，故是年有14个月。
  viii)唐上元2年（公元761年）九月去年号，但称元年。以建子为正，月以所建辰为名，原十月称亥月，原十一月称子月（岁首），...，原三月为辰月。而建巳月复寅正，恢复原月名，仍称四月。故辛丑年无十一月、十二月。壬寅年有十四个月。
另外，应当指出，本年历采用的都是实朔，而从春秋战国一直到唐初用的都是平朔，所以有在阴历日期上会有一日之差，应当说这是古人的不足。不过，古人常用日月食来校正日期（所谓观象授时），因而此时与本年历是吻合的。

  3.干支
  根据古代术数，年干支以立春为界，而月干支按节气月（从立春到雨水为一月，余类推）赋予，日干支以子时（从现代时间23时开始）为界。

  4.节气 
  本年历的节气全部采用定节气（最大误差不超过30分钟），但应注意我国古代历法知道清初才采用定节气，之前一直用平节气。

  5.朔望交食
  最大误差为3分钟，遇到日月食时，朔望时间可视为食甚时刻。由于所用时间均为北京时间，故他地须作时差转换，各地应根据日出日落时间来判断日月食能否看到。

  6.生肖星座
  生肖按年地支推出，故也以立春为界。十二星座可能在名称或日期范围上与有些资料不一致，但目前的状况确实如此。

  7.儒略日(Julian Day)
本年历的儒略日精确到时，以儒略历公元前4713年1月1日格林尼治时间正午12时为起点。


  8.各种节日
  公历节日，传统节日和名人纪念日，以及冬九九，夏三伏，梅雨季节等，但夏三伏，梅雨等等有不同说法，本年历按最常见的习惯制定。 


四、实例应用——在线万年历

  我的一个直接运用CCC编写的在线万年历的例子

  见Cal.htm或http://202.112.86.128/studentspace/aqyw/js/calendars/rili/cal.htm


五、作者的希望

  如果您有志于为中国日历类（CCC）做出自己的一分努力，那么就十分希望您能不断地宣传、交流甚或进一步完善摆在你面前的目前作者的这份阶段性工作。尤其是年代纪元，由于时间关系，我只输入至隋朝，但这已经把我弄得疲惫不堪了，我真希望谁能继续把这项
工作做完。在附件中我附上我国历史年表，大家可以参考。

</pre>
