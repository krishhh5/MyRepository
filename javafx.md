
### 在别的类调用start

Application.launch(类名.class,args);

### Application生命周期
- init();
- start();
- stop();
- 

### 设置舞台stage
- seTittle("");
- getIcons().add(new Image("图片路径");左上角图标
- setMaximized最大化
- close();
- setWidth();
- setHeight();
- setResizeble();是否可以改变大小
- setFullScreen(true);全屏
- setScene();
- setOpacity(0-1);舞台透明度
- setAlwaysOnTop();置顶
- setX();
- setY();坐标
- property.addListener();监听
initModality(Modality.Application_Model);阻止不关闭运行别的窗口
- 
- ### scene
- Scene scene = new Scene(组件);
- stage.setScene(scene);
- 
- ### 打开网页
- HostServices host = getHostServixes();
- host.showDocument("url");
- ### 布局类
- Group.getChildren().add(组件);addAlll(1,2,3);
- ### 组件
- setLayoutX();
- setLayoutY();位置
- setPreWidth();
- setPreHeight();
- setText();
- setFont();
- setBackground();
- setBorder();
- setOnAction(new EventHandler<ActionEvent>)
- {
-     });
- }
- 
### text
setPromptText();
setFont.font(40)
### BorderPane
BorderPane布局顶部，底部，左，右或中心区域中的子节点。每个区域只能有一个节点。BorderPane的顶部和底部区域允许可调整大小的节点占用所有可用宽度。左边界区域和右边界区域占据顶部和底部边界之间的可用垂直空间。
默认情况下，所有边界区域尊重子节点的首选宽度和高度。放置在顶部，底部，左侧，右侧和中心区域中的节点的默认对齐方式如下：
- 
- 顶部: Pos.TOP_LEFT
- 底部: Pos.BOTTOM_LEFT
- 左侧: Pos.TOP_LEFT
- 右侧: Pos.TOP_RIGHT
- 中心: Pos.CENTER
- 
```
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.stage.Stage;

public class Main extends Application {

    public static void main(String[] args) {
        Application.launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Title");
        Group root = new Group();
        Scene scene = new Scene(root, 400, 250, Color.WHITE);
```

        MenuBar menuBar = new MenuBar();
        EventHandler<ActionEvent> action = changeTabPlacement();

        Menu menu = new Menu("Direction");
        MenuItem left = new MenuItem("Left");

        left.setOnAction(action);
        menu.getItems().add(left);

        MenuItem right = new MenuItem("Right");
        right.setOnAction(action);
        menu.getItems().add(right);

        MenuItem top = new MenuItem("Top");
        top.setOnAction(action);
        menu.getItems().add(top);

        MenuItem bottom = new MenuItem("Bottom");
        bottom.setOnAction(action);
        menu.getItems().add(bottom);

        menuBar.getMenus().add(menu);

        BorderPane borderPane = new BorderPane();

        borderPane.prefHeightProperty().bind(scene.heightProperty());
        borderPane.prefWidthProperty().bind(scene.widthProperty());

        borderPane.setTop(menuBar);

        root.getChildren().add(borderPane);

        primaryStage.setScene(scene);
        primaryStage.show();
    }// from w WW.y i i   bAI. c OM

    private EventHandler<ActionEvent> changeTabPlacement() {
        return new EventHandler<ActionEvent>() {

            public void handle(ActionEvent event) {
                MenuItem mItem = (MenuItem) event.getSource();
                String side = mItem.getText();
                if ("left".equalsIgnoreCase(side)) {
                    System.out.println("left");
                } else if ("right".equalsIgnoreCase(side)) {
                    System.out.println("right");
                } else if ("top".equalsIgnoreCase(side)) {
                    System.out.println("top");
                } else if ("bottom".equalsIgnoreCase(side)) {
                    System.out.println("bottom");
                }
            }
        };
    }
}

### FlowPane布局
1- FlowPane布局FlowPane是一个容器。它在一行上排列连续的子组件，并且如果当前行填满了以后，则自动将子组件向下推到下一行

### HBox
HBox布局类将JavaFX子节点放在水平行中。 新的子节点附加到右侧的末尾。默认情况下，HBox布局尊重子节点的首选宽度和高度。当父节点不可调整大小时，例如Group节点，HBox的行高度设置为子节点的最大首选高度。
默认情况下，每个子节点与左上(Pos.TOP_LEFT)位置对齐。
我们可以通过编程方式改变HBox的布局约束，例如边框，填充，边距，间距和对齐。
当处理不可缩放的子节点(如Shape节点)时，父节点会考虑Shape的矩形边界(ParentInBounds)的宽度和高度。
当处理诸如TextField控件之类可调整大小的节点时，父节点计算TextField水平增长的可用空间。
要在HBox中水平增长UI控件，请使用静态HBox.setHgrow()方法。



