# FramelessWindow-Qt
Custom frameless window,dialog,messagebox  Library / 自定义无边框窗体，对话框和提示框，并封装成库

FlyWM_
GitHub: https://github.com/FlyWM
CSDN: https://blog.csdn.net/a844651990

使用方法：
#include "framelesswindow.h"
#include <QWidget>
#include <QApplication>

int main(int argc, char *argv[])
{
    QApplication a(argc, argv);

    // FramelessWindow
    FramelessWindow *pWindow = new FramelessWindow();
    QWidget *pCentralWidget = new QWidget(pWindow);
    pWindow->setCentralWidget(pCentralWidget);
    pWindow->show();
    
    // FramelessDialog
    FramelessDialog *pDialog = new FramelessDialog(pWindow);
    QWidget *pDlgCentralWidget = new QWidget(pDialog);
    QPushButton *pButton = new QPushButton(pDlgCentralWidget);
    pDialog->setCentralWidget(pDlgCentralWidget);
    pDialog->setModal(true);
    pDialog->show();
    
    // FramelessMessageBox
    FramelessMessageBox::showInformation(pWindow, QObject::tr("提示!"), QObject::tr("自定义提示框！"));
    return a.exec();
}

