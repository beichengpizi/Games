1 软件功能与架构设计
1 、 功能分析
1) 战斗系统
➢ 玩家需要用各种植物来防御一波波不断涌来的僵尸。如果将所有的僵尸消灭，就可以顺利过关。
➢ 在每关携带的卡牌中选择合适的植物放置在战斗区域上，每种植物都有自己的攻击方式和特定的作用。例如，豌豆射手可以向前发射豌豆来攻击僵尸，坚果墙可以阻挡僵尸前进等。
➢ 战斗区域分为多个小格子，玩家需要在有限的位置上种植植物。
2) 植物系统
➢ 游戏中拥有多种不同类型的植物，每种植物都有不同的属性，包括攻击类型、在游戏中需要耗费的阳光数量、攻击范围、伤害值、自身生命值等等。
➢ 玩家拥有一个植物牌组，其中包括多种植物卡片，需要在游戏中选择不同的植物卡牌进行战斗。植物卡片可以通过通关关卡获得。
➢ 植物根据其功能分类可分为：攻击系、阳光系、消耗系、防御系、控制系、近战系、强化系、辅助系。
3) 场景设定
➢ 游戏中有白天和黑夜两个场景，白天场景中会随机掉落阳光，用于种植植物，而黑夜场景中不会掉落阳光，因此玩家只能通过向日葵等生产阳光的植物来收集阳光。不同
的植物在不同的场景中有不同的作用，例如，对于铁桶僵尸，可以用磁力菇将僵尸的铁桶吸走，从而降低僵尸的防御。
➢ 玩家需要根据不同场景的属性来规划和部署合适的植物组合，以便在战斗中取得胜利。
4) 僵尸系统
➢ 游戏中有多重不同的僵尸，每种僵尸都有不同的特点和攻击方式。例如，橄榄球僵尸会以快于普通僵尸的速度向前冲刺，直到遇到第一个植物才会停下来，并且直接杀死面前的植物；撑杆跳僵尸可以越过第一个植物等。
➢ 每个僵尸的生命值不同，当僵尸所受到的植物攻击超过僵尸自身生命值后，僵尸将死亡。
➢ 僵尸死亡的方式有两种，一种是受到普通攻击死去，例如被豌豆射手发射的子弹打死、或被卷心菜投手投出的卷心菜打死，另一种是被炸弹炸死，这种死法的僵尸尸体呈烧焦状，例如被樱桃炸弹炸死或被土豆地雷炸死，还有一种死法是被食人花吃掉，
这种死法的僵尸并未留下尸体。
➢ 每种僵尸都有不同的弱点，例如，撑杆跳僵尸可以用高坚果筑起高墙阻止僵尸越过防线。
5) 关卡设计
➢ 游戏中有 12 个难度不同的关卡，每个关卡都有不同的僵尸种类和数量。关卡之间的难度逐渐增加，玩家需要不断提升自己的策略才能够完成更高难度的挑战。
➢ 每次通过一个关卡，玩家都会得到一个新的植物，并且在后面的关卡中玩家可以使用新获得的植物。
➢ 如果并未通过某关卡，将无法使用通关该关卡可获得的植物卡片。
2、模块划分
1) 资源管理模块：负责管理游戏中使用的各种资源，如图片素材、音效、字体等。该模块主要用于压缩和加载游戏资源，以保证游戏的流畅性和稳定性。
2) 界面系统模块：负责游戏中的各种 UI 界面，如主菜单、游戏界面、植物图鉴等。此外，该模块还要实现各种交互和动态特效等等。
3) 战斗模块：实现游戏的核心战斗系统，创建和管理游戏中的各种植物和僵尸对象，并控制它们的位置、运动和攻击等行为。该模块还需要处理游戏场景中各种阻碍和障碍，使角色可以顺利地攻击和移动。
4) 植物模块：负责植物的创建、销毁和运动行为，管理植物的属性和状态，如攻击敢为、攻击力、耐久度等，该模块还需要处理植物特有的行为，如发射攻击、产生阳光、自动爆炸等等。
5) 僵尸模块：与植物模块类似，负责僵尸的安防、销毁和运动行为，管理僵尸的属性和状态，该模块还需要处理每种僵尸特有的行为，如挖掘地道、爆炸自毁等等。
6) 道具模块：管理游戏中的各种道具，如阳光、炸弹等等。该模块还要处理道具的使用和消耗逻辑，以及增加或减少玩家的虚拟货币等。
7) 数据管理模块：负责存储和读取游戏中的各种数据，如植物的属性、僵尸的属性、玩家的游戏进度等。该模块需要使用数据库或文件存储数据，以便保留玩家的游戏数据。
3、业务流程图 业务流程图
1) 主界面：
➢ 玩家进入游戏后，会首先看到游戏的主界面，支持对游戏的开始、设置、退出等操作。
➢ 根据用户的操作，将会从服务器获取相关数据，如玩家属性、植物、僵尸、开放的关卡等，并根据用户的操作更新到界面中。
2) 关卡选择
➢ 用户在游戏主界面选择开始游戏后，会进入到关卡选择界面。
➢ 玩家可以在此选择需要进行的关卡和场景模式，并开始进行游戏。
3) 游戏初始化
➢ 当用户选择要玩的关卡后，游戏会初始化以获取关卡中需要的所有虚拟物品和游戏角色等相关信息，同时也会设置界面的相关属性，如显示信息的布局、背景色、音乐等等。
4) 游戏过程
➢ 游戏过程中，玩家需要种植不同的植物，以防止泛滥的僵尸传入防线。
➢ 游戏过程中需要保持策略上的连贯性，防止僵尸占领防线，当玩家的植物、防线或其他面向玩家的要素被摧毁或者被击败，游戏就失败了。
5) 游戏结算
➢ 当玩家陈宫地战胜所有僵尸后，游戏就会结束并出现新获得的卡牌，玩家可以选择进行下一关游戏。
6) 植物图鉴
➢ 玩家可以在游戏开始界面选择打开植物图鉴，查看各种植物的属性。
4、软件架构设计
1) 总体架构
➢ 植物大战僵尸的整个系统采用客户端-服务器架构，主要分为前端客户端和后端服务器两个部分。
➢ 前端客户端主要负责游戏的展示和用户交互，包括游戏的各种 UI 界面、游戏的核心战斗系统、音频和动画效果等。
➢ 后端服务器主要负责处理游戏数据的存取、游戏逻辑的计算等一系列操作，提供与前端客户端的通信接口，以维持客户端的共享状态。
2) 前端架构
➢ 前端架构采用基于 MVC 架构（Model-View-Controller）来设计，实现了视图、控制器和模型三个部分的分离。
➢ 模型（Model）主要负责游戏数据的处理，如植物、僵尸、场景、关卡和道具等，它们是游戏逻辑的核心组件。模型以数据对象的形式存储在内存中，实现了各种业务逻
辑和行为，如控制植物的生长、僵尸的攻击，场景的生成和销毁等。模型部分中的类共分为四种：控制植物的类、控制僵尸的类、控制子弹的类。
管理植物的类及各个类的功能如下所示：
类 实现功能
CabbagePault 控制卷心菜投手投掷卷心菜攻击僵尸
Cactus 控制仙人掌发射尖刺攻击僵尸
CherryBomb 控制樱桃炸弹将僵尸炸成灰烬
Chomper 控制食人花吞噬并咀嚼僵尸
DoomShroom 控制毁灭菇爆炸并消灭大批僵尸
Garlic 控制大蒜，使吃到大蒜的僵尸改变轨迹
GatlingPea 控制机枪豌豆射手连续发射四颗豌豆子弹攻击僵尸
IceShroom 控制寒冰菇在僵尸接近的时候冰冻他们，形成一个缓冲区
Jalapeno 控制火爆辣椒在僵尸接近的时候燃烧，烧死一整列的僵尸
MelonPult 控制西瓜投手投射出西瓜对僵尸造成伤害
KernelPult 控制玉米投手投射出玉米粒或者黄油对僵尸造成伤害
Peashooter 控制豌豆射手发射豌豆对僵尸造成伤害
Plant 控制植物状态：安全或正在受到攻击或死亡
Plantern 控制路灯花驱散夜晚出现的迷雾
PotatoMine 控制土豆地雷沉睡或启动状态，土豆地雷沉睡时遇到僵尸会直接被
僵尸吃掉，启动后会炸飞踩到它的僵尸
Repeater 控制双重射手一次发射两颗豌豆攻击僵尸
SnowPea 控制寒冰射手发射寒冰子弹，可以减速僵尸
Spikerock 控制钢地刺攻击踩到它的僵尸
SpikeWeed 控制地刺攻击踩到它的僵尸
SplitPea 控制双向射手分别向前后发射子弹攻击僵尸
Squash 控制窝瓜压死接近它的僵尸
StarFruit 控制星星果分别向五个方向发射星星子弹攻击僵尸
SunFlower 控制向日葵每隔一段时间产生 25 点阳光
TallNut 控制高坚果竖起一座高墙保护身后的植物
Threepeater 控制三线射手分别在三行路线上发射豌豆子弹
Torchwood 控制火炬树桩使穿过它的普通子弹变成火焰子弹
TwinSunflower 控制双子向日葵更快速的产生阳光
WallNut 控制坚果竖起一堵墙保护身后的植物
管理僵尸的各个类及其功能如下所示：
类 实现功能
Zombie 控制普通僵尸、路障僵尸、铁桶僵尸进行攻击，同时根据僵尸受
到攻击的情况管理僵尸的生命值
PoleVaultingZombie 控制撑杆跳僵尸越过距离它最近的植物，僵尸撑杆跳一次后失去
支撑杆成为普通僵尸
FootballZombie 控制橄榄球僵尸以快于其他僵尸的速度向前冲刺，直到踩死最前
面的一棵植物才会停下，防御较高
NewspaperZombie 控制读报僵尸在报纸未被植物击破前以较慢的速度前进，报纸被
植物击破后感到愤怒，从而加快前进速度，同时攻击力增加
管理子弹的类：
类 实现功能
Bullet 控制子弹的移动，并判断子弹是普通子弹还是火焰子弹
CactusBullet 控制仙人掌尖刺的移动，并对僵尸进行攻击
PeaBullet 控制豌豆射手子弹的发射，并对僵尸进行攻击
SnowBullet 控制寒冰射手子弹的移动，被寒冰射手伤害的僵尸将产生冰冻效果并减速
StarBullet 控制星星果子弹的移动，并对僵尸进行攻击
Sun 控制阳光的数量，并在种下植物和收集阳光时对阳光进行增减
ThreeBullet 控制三线射手子弹的移动，攻击僵尸
➢ 视图（View）主要负责 UI 界面的渲染，包括游戏背景、植物、僵尸、道具、水印等。视图通过计算调用控制器中的方法，以相应游戏中的操作和事件，实现视图与模型的交互。
管理UI界面的类及其功能如下所示：
类 实现功能
AlmanacLayer 植物图鉴界面，用户可以点击想查看的植物卡牌来查看植物属性
AlongAlanLayer 关卡通关界面，展示新获得的植物卡牌，可以点击进入下一关
CheckSelectorLayer 游戏关卡选择界面，可以选择想要体验的游戏关卡和白天黑夜模式。
CombatLayer 植物卡牌选择界面，可以预览本关将要出现的僵尸。
LogoLayer 打开 app 后出现游戏开发者 logo 和原版游戏公司 Logo。
MenuLayer 菜单界面，可以选择开始游戏或者查看图鉴。
PauseLayer 暂停界面，可以暂停游戏然后选择返回游戏或者返回主菜单或者查看植物图鉴。
➢ 控制器（Controller）主要负责游戏的控制和逻辑处理，控制游戏流程，如游戏的启动、结束和重启。同时处理玩家交互动作和表现发挥的行为，如种植植物，攻击僵尸等等。控制器主要通过触发模型和视图的方法来实现游戏逻辑的处理。
控制游戏和逻辑处理的类及其功能：
类 实现功能
CombatLine 游戏界面，玩家可以种植植物。
3) 后端架构
➢ 后端架构采用基于 SOA 架构（Service-oriented architecture）的设计，以保障游戏的高可靠性、高可扩展性、高并发性。
➢ 后端主要分为服务层（Service Layer）、数据层（Data Access Layer）和存储层（Database Layer）三个部分。
➢ 服务层负责处理游戏数据的访问和管理，如植物、僵尸、场景、关卡等数据的读取、修改和删除。服务层主要提供游戏的核心业务逻辑。
➢ 数据层负责和数据库进行交互，实现数据库中数据的读取和存储。
➢ 数据层还要实现数据访问的 ORM 映射，使用 ORM 框架实现业务对象，ORM 框架将各种数据对象和 SQL 语句进行映射和转换，使得开发人员可以通过对象来访问数据库中的数据。
➢ 存储层主要负责实现数据的持久化存储和管理，包括数据库的实现。
管理数据库的类及其功能：
类 实现功能
DBManager 对数据库进行增删查改等操作
MyDatabaseHelper 创建一个数据库
4 软件开发与实现
1、软件开发工具及版本 软件开发工具及版本
➢ Android Studio Arctic Fox| | 2020.3.1 ：
这是一款谷歌官方最新推出的 Android 应用开发工具，在原版的基础上改进了 Gradle构建系统，同时支持构件缓存与增量构建；除此之外，还内置了设备模拟器，支持多种设备和 Android 系统版本的模拟。
➢ Android Gradle Plugin:3.0.1
这是谷歌为 Android 应用开发提供的一款构建工具，是 Gradle 构建系统的一部分，可以提供一整套构建和自动化工作流，管理和构建 Android 项目所需的文件等资源。
➢ Gradle：4.4.1
在 Android 开发中，Gradle 是一种高效地自动化构建工具，用于构建和构造 Android应用程序的项目。在 Android Studio 中，Gradle 用作应用程序的构建工具，负责编译。打包和发布应用程序。
➢ GradleJDK:1.8
使用 Gradle 构建项目时所依赖的 JDK 版本。JDK（Java Development Kit）是 Java 开发工具包的缩写，包括了 Java 的运行环境、Java 工具和 Java 基础类库等组成部分。
➢ 游戏引擎： Cocos2d
Cocos2d 是一个开源的游戏引擎，用于快速开发 2D 游戏和其他图形应用程序，可以开发多平台的游戏，包括 iOS、Android、Windows、Mac、Web 等。Cocos2d 是一个功能强大而又易于使用的游戏引擎，能够帮助开发者快速开发高质量的 2D 游戏和其他图形应用程
序。同时，跨平台支持可以为开发者节省很多时间和开发成本，大大提高开发效率。
➢ 模拟器型号： 10.1 WXGA(Tablet) API 27
2、重要功能的编程实现方法 重要功能的编程实现方法
1）游戏场景切换
CCSprite ccSprite_logo1= CCSprite.sprite("logo/logo1.png");
CGSize winSize= CCDirector.sharedDirector().winSize();//获取游戏窗口的尺寸，包含了当前窗口的高度和宽度
ccSprite_logo1.setPosition(winSize.getWidth()/2,winSize.getHeight()/2);//并设置游戏画面显示的位置
addChild(ccSprite_logo1);//将游戏曾添加到场景中
CCDelayTime ccDelayTime= CCDelayTime.action(2);//延迟两秒后执行切换场景
CCHide ccHide= CCHide.action();
CCCallFunc ccCallFunc= CCCallFunc.action(this,"logo2");//回调函数
CCSequence ccSequence= CCSequence.actions(ccDelayTime,ccHide,ccCallFunc);//创建连续的动作序列
ccSprite_logo1.runAction(ccSequence);//执行动画效果
2）添加 CG(Computer Graphics) 动画
// 创建一个新精灵对象 ccSprite_cg 并将资源 bg.jpg 加载进去
CCSprite ccSprite_cg= CCSprite.sprite("cg/bg.jpg");
// 将 ccSprite_cg 添加到 GameLayer
addChild(ccSprite_cg);
// 获取屏幕的尺寸并-save
CGSize winSize = CCDirector.sharedDirector().getWinSize();
// 设置 ccSprite_cg 的位置为屏幕中心 -save
ccSprite_cg.setPosition(winSize.getWidth()/2,winSize.getHeight()/2);
// 将 ccSprite_cg 的宽度设置为屏幕宽度的比例 -save
// 以保证图片的宽度和屏幕宽度相同
ccSprite_cg.setScaleX(winSize.getWidth()/ccSprite_cg.getTextureRect().size.getWidth());
// 将 ccSprite_cg 的高度设置为屏幕高度的比例 -save
// 以保证图片的高度和屏幕高度相同
ccSprite_cg.setScaleY(winSize.getHeight()/ccSprite_cg.getTextureRect().size.getHeight());
// 加载 loading_01.png 并创建一个新精灵对象 loding
CCSprite loding = CCSprite.sprite("cg/loading_01.png");
// 将 loding 精灵添加到 GameLayer
loding.setPosition(winSize.getWidth()/2,80);
loding.setScale(1.9);
addChild(loding);
// 加载 loading_01.png 到 loading_10.png 并将它们封装为一个 ArrayListCCSpriteFrame
ArrayList<CCSpriteFrame> frames=new ArrayList<>();
for (int i = 1; i <11 ; i++) {
2023 移动项目实践-大作业
CCSpriteFrame ccSpriteFrame= CCSprite.sprite(String.format(Locale.CHINA,"cg/loading_%02d.png",i)).displayedFrame();
frames.add(ccSpriteFrame);
}
// 使用 frames 中提供的所有帧，创建一个新动画对象 ccAnimation，并设置帧之间的间隔时间为 0.2 秒
CCAnimation ccAnimation= CCAnimation.animationWithFrames(frames,0.2f);
// 使用 ccAnimation 创建一个新的 ccAnimate 对象，并向左边重复播放动画效果。
// 最后，将 ccAnimate 与 CCCallFunc 组合形成 CCSequence
// 作为 loding 精灵的动作列表标准，并将其传递给 runAction() 方法执行。
CCAnimate ccAnimate= CCAnimate.action(ccAnimation,false);
CCCallFunc ccCallFunc= CCCallFunc.action(this,"setTouch");
CCSequence ccSequence= CCSequence.actions(ccAnimate,ccCallFunc);
loding.runAction(ccSequence);
3 ） 按钮设置
// 创建一个新菜单
CCMenu ccMenu= CCMenu.menu();
// 在“开始冒险”按钮的默认状态下创建一个 CCSprite 对象
CCSprite ccSprite_start_adventure_default=CCSprite.sprite("menu/start_adventure_default.png");
// 创建“开始冒险”按钮按下状态下的 CCSprite 对象
CCSprite ccSprite_start_adventure_press=CCSprite.sprite("menu/start_adventure_press.png");
// 创建 MenuItemSprite 对象，该对象包含默认状态下和按下状态下的 CCSprite
// 封装了触控后响应的处理方法“start”，position（菜单位置），this（GameLayer 为Menu Delegate）
CCMenuItemSprite ccMenuItemSprite= CCMenuItemSprite.item(ccSprite_start_adventure_default, ccSprite_start_adventure_press,this,"start");
// 设置菜单项的位置
ccMenuItemSprite.setPosition(270,160);
// 将 MenuItemSprite 添加到菜单中。
ccMenu.addChild(ccMenuItemSprite);
// 将菜单添加到层中。
1. addChild(ccMenu);
4 ）背景音乐设置
// 静态方法 bgmSound 用于播放背景音乐。
// 其中，id 表示要播放的背景音乐的资源 ID。
public static void bgmSound(int id){
// 如果开启了背景音乐则播放音乐
if (isBGMSound){
// 调用 SimpleAudioEngine 提供的 playSound 方法来播放背景音乐
// 该方法接收三个参数：当前 Activity、音乐资源 ID、是否重复播放
ToolsSet.bgm.playSound(CCDirector.sharedDirector().getActivity(), id,true);
}
}
5 5 ）植物攻击僵尸
// 当攻击结束的时候，就会执行 launchEnd() 方法
@Override
public void launchEnd(){
// 获取当前子弹对象，并将其从场景中移除。
getBullet().removeSelf();
// 创建动作，延迟 2.9 秒后执行 noAtt() 方法，攻击结束，可以执行下一次攻击
CCDelayTime ccDelayTime = CCDelayTime.action(2.9f);
CCCallFunc ccCallFunc = CCCallFunc.action(this,"noAtt");
CCSequence ccSequence = CCSequence.actions(ccDelayTime,ccCallFunc);
// 执行动作
runAction(ccSequence);
// 播放击中飞行路径上的一系列动画
// 创建另一个精灵，以获取它的父对象（当前操作对象的父层）
AEffect head = new AEffect("eff/boom3/effect_f01_%02d.png",9,9*0.1f,0.1f);
// 设置其位置，使其出现在击中的位置
head.setPosition(getIntentPoint());
getParent().addChild(head,6);
// 播放爆炸音效
ToolsSet.effectSound(R.raw.bomb1);
// 计算攻击量，并扣除僵尸的相应生命值
getZombie().hurtCompute(getHurt());
// 如果僵尸无生命值，则将其标记为死亡状态，并从场景中移除
if (getZombie().getHP() == 0) {
getZombie().death(0);
getZombie().removeSelf();
}
}
6 6 ）数据库 建立
//定义一个名为 MyDatabaseHelper 的类，它继承于 SQLiteOpenHelper 类
public MyDatabaseHelper(Context context){
//调用 SQLiteOpenHelper 的构造函数，并传入数据库的名称（pvz.db），工厂类（null）和版本
号（1）
super(context,"pvz.db",null,1);
}
@Override
//当数据库第一次被创建时，该方法被调用，用于创建数据库表
public void onCreate(SQLiteDatabase db) {
//定义字符串变量 sql，用于存放对 plant 表进行创建的 SQL 语句
String sql = "create table plant(_id integer primary key autoincrement,plant_id
integer unique not null,name text not null,price integer not null,type text not nu
ll,heartpoint integer not null)";
//定义字符串变量 sql2，用于存放对 zombies 表进行创建的 SQL 语句
String sql2= "create table zombies(_id integer primary key autoincrement,zombie
s_id integer unique not null,name text not null,heartpoint integer not null)";
//定义字符串变量 sql3，用于存放对 level 表进行创建的 SQL 语句
String sql3= "create table level(max text not null,level integer not null)";
//执行 SQL 语句来创建三个数据库表
db.execSQL(sql);
db.execSQL(sql2);
db.execSQL(sql3);
}
7 ）数据库操作
//定义一个名为 initDB 的静态函数，用于在应用程序启动时初始化数据库
public static void initDB(Context context){
//创建 MyDatabaseHelper 对象，传入应用程序的上下文对象
MyDatabaseHelper dbHelper=new MyDatabaseHelper(context);
//获取可写的数据库
database=dbHelper.getWritableDatabase();
}
//定义一个名为 addplantInfo 的静态函数，用于向数据库中插入植物信息
public static long addplantInfo(int plant_id,String name,int price,String type,int
heartpoint){
//新建一个 ContentValues 对象，用于保存插入的数据
ContentValues values=new ContentValues();
//将传入的植物信息保存到 ContentValues 对象中
values.put("plant_id",plant_id);
values.put("name",name);
values.put("price",price);
2023 移动项目实践-大作业
values.put("type",type);
values.put("heartpoint",heartpoint);
//插入数据到名为 plant 的数据库表中
return database.insert("plant",null,values);
}
//定义一个名为 queryInfoBylevel 的静态函数，用于根据关卡名称查询关卡信息
public static String queryInfoBylevel(String max){
//使用查询方法，从名为 level 的数据库表中查询关卡名称为 max 的所有数据
Cursor cursor = database.query("level", null, "max=?", new String[]{max}, null,
null, null);
//如果有数据，将光标移到第一行，并获取 level 字段中的内容，返回这个内容
if (cursor.getCount()>0) {
cursor.moveToFirst();
String content = cursor.getString(cursor.getColumnIndex("level"));
return content;
}
//如果没有数据，则返回 null
return null;
}
//定义一个名为 queryAllplantid 的静态函数，用于查询所有的植物 ID
public static List<Integer> queryAllplantid(){
//使用查询方法，从名为"plant"的数据库表中查询所有数据
Cursor cursor = database.query("plant", null, null, null, null, null,null);
//定义一个 List 对象，用于保存查询结果中的植物 ID
List<Integer> plantList = new ArrayList<>();
//遍历查询结果，将植物 ID 添加到 List 对象中
while (cursor.moveToNext()) {
int plantid = cursor.getInt(cursor.getColumnIndex("plant_id"));
plantList.add(plantid);
}
//返回 List 对象
return plantList;
}
//定义一个名为 updateInfoBymax 的静态函数，用于更新关卡信息
public static int updateInfoBymax(String max,int content){
//新建一个 ContentValues 对象，用于保存要更新的数据，将传入的 content 值赋值给 level 字段
ContentValues values = new ContentValues();
values.put("level",content);
//使用 update 函数更新名为 level 的数据库表中，max 等于传入参数 max 的值，并将 level 字段
更新为 content 的值
return database.update("level",values,"max=?",new String[]{"max"});
}
