QSplitter如果是在QWindow上使用会导致窗体上不能有其他任何控件
这个Demo展示可以让QSplitter在任意Qwidget上的使用方法，这样可以实现多个画面和控件共存在一个页面。
QSplitter的一个好处是，整个窗体放大和缩小，QSplitter都可以进行自适应。
今天想在一个QWidget上布置一个splitter，结果怎么都放不上去，后来发现这个QWidget上有个Layout，使用这个Layout就能正常显示了

    QSplitter *splitterMain = new QSplitter(Qt::Vertical);

    splitterMain->setHandleWidth(1);
    splitterMain->addWidget(K1);
    splitterMain->addWidget(K2);
    this->setFocusPolicy(Qt::StrongFocus);
    QVBoxLayout * stockShowLayout = new QVBoxLayout;
    //stockShowLayout->addWidget(splitterMain);
    //ui->page_2->addWidget(stockShowLayout);  这个layout始终不起作用
    ui->verticalLayout_8->addWidget(splitterMain);//固有的layout可以用
