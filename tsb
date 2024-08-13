#include <graphics.h>
#include <conio.h>
#include <Windows.h>
#include <iostream>
using namespace std;

struct RGBColor
{
	TCHAR redVal[12];
	TCHAR greenVal[12];
	TCHAR blueVal[12];
};

RGBColor stoT(BYTE red, BYTE green, BYTE blue) {

	RGBColor saveRgb;

	swprintf_s(saveRgb.redVal, _T("%d"), red);
	swprintf_s(saveRgb.greenVal, _T("%d"), green);
	swprintf_s(saveRgb.blueVal, _T("%d"), blue);

	return saveRgb;
}

int main() {

	//TCHAR redVal[10];
	//TCHAR greenVal[10];
	//TCHAR blueVal[10];

	initgraph(640, 480);	// 创建绘图窗口，大小为 640x480 像素


	LOGFONT f;
	gettextstyle(&f);						// 获取当前字体设置
	f.lfHeight = 48;						// 设置字体高度为 48
	wcscpy_s(f.lfFaceName, _T("楷体"));		// 设置字体为“黑体”(高版本 VC 推荐使用 _tcscpy_s 函数)
	f.lfQuality = ANTIALIASED_QUALITY;		// 设置输出效果为抗锯齿  
	settextstyle(&f);						// 设置字体样式

	int wdheight = getheight();
	int wdwidth = getwidth();


	//1、绘制图形
	BYTE setRed = 0;
	BYTE setGreen = 0;
	BYTE setBlue = 0;

	RGBColor changedRgb = stoT(setRed, setGreen, setBlue);

	settextcolor(RGB(100, 0, 0));
	outtextxy(0, 0, changedRgb.redVal);

	settextcolor(RGB(0, 100, 0));
	outtextxy(0 + (wdwidth / 3) * 1, 0, changedRgb.greenVal);

	settextcolor(RGB(0, 0, 100));
	outtextxy(0 + (wdwidth / 3) * 2, 0, changedRgb.blueVal);

	setlinecolor(RGB(setRed, setGreen, setBlue));
	rectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);

	TCHAR keyy[10];

	while (true)
	{
		RGBColor changedRgb = stoT(setRed, setGreen, setBlue);
		settextcolor(RGB(100, 50, 0));

		settextcolor(RGB(100, 0, 0));
		outtextxy(0, 0, changedRgb.redVal);

		settextcolor(RGB(0, 100, 0));
		outtextxy(0 + (wdwidth / 3) * 1, 0, changedRgb.greenVal);

		settextcolor(RGB(0, 0, 100));
		outtextxy(0 + (wdwidth / 3) * 2, 0, changedRgb.blueVal);

		setlinecolor(RGB(setRed, setGreen, setBlue));
		rectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);

		setfillcolor(RGB(setRed, setGreen, setBlue));
		setlinecolor(RGB(setRed, setGreen, setBlue));
		fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
		if (_kbhit) {
			char key = _getch();
			_itow_s(key, keyy, 10);
			settextcolor(RGB(100, 0, 0));

			//cleardevice();
			//outtextxy(0, 0, keyy);

			cleardevice();
			settextcolor(RGB(100, 0, 0));
			outtextxy(0, 0, changedRgb.redVal);
			setfillcolor(RGB(setRed, setGreen, setBlue));
			setlinecolor(RGB(setRed, setGreen, setBlue));
			fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);

			//2、检测按键输入，如果是R 就更改setRed的值
			if (key == 114 || key == 82) {  //如果按下了R键，代表要更改其中的R值
				// 2-1、绘制按下了R键的界面

				cleardevice();
				settextcolor(RGB(100, 0, 0));
				outtextxy(0, 0, changedRgb.redVal);
				setfillcolor(RGB(setRed, setGreen, setBlue));
				setlinecolor(RGB(setRed, setGreen, setBlue));
				fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
				while (true)
				{
					if (_kbhit) {
						char key = _getch();
						_itow_s(key, keyy, 10);
						if (key == 72) {  //2-2、按下了方向键上，表示要向上调整R值
							setRed++;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行加加

							settextcolor(RGB(100, 0, 0));
							outtextxy(0, 0, changedRgb.redVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 80) {  //2-3、按下了方向键下，表示要向下调整R值
							setRed--;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行减减

							settextcolor(RGB(100, 0, 0));
							outtextxy(0, 0, changedRgb.redVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 27) {
							break;
						}
					}
				}

			}


			//2、检测按键输入，如果是G 就更改setGreen的值  (103)
			if (key == 103 || key == 71) {  //如果按下了R键，代表要更改其中的R值
				// 2-1、绘制按下了R键的界面

				cleardevice();
				settextcolor(RGB(0, 100, 0));
				outtextxy(0 + (wdwidth / 3) * 1, 0, changedRgb.greenVal);
				setfillcolor(RGB(setRed, setGreen, setBlue));
				setlinecolor(RGB(setRed, setGreen, setBlue));
				fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
				while (true)
				{
					if (_kbhit) {
						char key = _getch();
						_itow_s(key, keyy, 10);
						if (key == 72) {  //2-2、按下了方向键上，表示要向上调整R值
							setGreen++;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行加加

							settextcolor(RGB(0, 100, 0));
							outtextxy(0 + (wdwidth / 3) * 1, 0, changedRgb.greenVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 80) {  //2-3、按下了方向键下，表示要向下调整R值
							setGreen--;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行减减

							settextcolor(RGB(0, 100, 0));
							outtextxy(0 + (wdwidth / 3) * 1, 0, changedRgb.greenVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 27) {
							break;
						}
					}
				}

			}


			//2、检测按键输入，如果是B 就更改setBlue的值  (103)
			if (key == 98 || key == 66) {  //如果按下了R键，代表要更改其中的R值
				// 2-1、绘制按下了R键的界面

				cleardevice();
				settextcolor(RGB(0, 0, 100));
				outtextxy(0 + (wdwidth / 3) * 2, 0, changedRgb.blueVal);
				setfillcolor(RGB(setRed, setGreen, setBlue));
				setlinecolor(RGB(setRed, setGreen, setBlue));
				fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
				while (true)
				{
					if (_kbhit) {
						char key = _getch();
						_itow_s(key, keyy, 10);
						if (key == 72) {  //2-2、按下了方向键上，表示要向上调整R值
							setBlue++;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行加加

							settextcolor(RGB(0, 0, 100));
							outtextxy(0 + (wdwidth / 3) * 2, 0, changedRgb.blueVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 80) {  //2-3、按下了方向键下，表示要向下调整R值
							setBlue--;
							RGBColor changedRgb = stoT(setRed, setGreen, setBlue);	//对rgb值进行减减

							settextcolor(RGB(0, 0, 100));
							outtextxy(0 + (wdwidth / 3) * 2, 0, changedRgb.blueVal);
							setfillcolor(RGB(setRed, setGreen, setBlue));
							setlinecolor(RGB(setRed, setGreen, setBlue));
							fillrectangle((wdwidth / 4), (wdheight / 4), (wdwidth / 4) * 3, (wdheight / 4) * 3);
						}

						if (key == 27) {
							break;
						}
					}
				}

			}

			if (key == 27) {
				break;
			}

		}
	}

	int ch = _getch();		// 按任意键继续
	closegraph();			// 关闭绘图窗口
	return 0;
}
