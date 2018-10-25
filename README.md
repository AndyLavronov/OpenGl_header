WinOpenGL
Все что нужно для работы с OpenGL на Windows.

Подробная инструкция по подключению.

1. Заходим на https://www.opengl.org/resources/libraries/glut/ скачиваем архив с хидер файлами

2. После того как он скачался, делаем его разархивацию.

3. Создаем папку OpenGL_libs и скидываем туда файлы

4. Файлы glut32.dll закидываем в  диск С:\Windows\System

5. Дальше открываем Visual Studio ищем его расположение 

6. Дальше скидываем файлы glut.dll и glut32.dll в папку C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\TeamFoundation\Team Explorer\Git\mingw32\lib\engines

7. Открываем Visual Studio и создаем пустой проект на visual c++

8. В обозревателе решений слева правой клавишой мыши кликаем по проекту и нажимаем кнопку добавить

9. Выбираем все нужные нам для работы библиотеки с  папки OpenGl_libs и приступаем к работе.


TEST CODE 
 |
 |
 V


#include <glut.h>

void Display() {
 glClear(GL_COLOR_BUFFER_BIT);
 glFlush();
}

void Initialize() {
 glClearColor(0.8, 1.0, 0.6, 1.0);
 glMatrixMode(GL_PROJECTION);
 glLoadIdentity();
 glOrtho(-200.0, 200.0, -200.0, 200.0, -5.0, 5.0);
}

int main(int argc, char ** argv) {
 glutInit(&argc, argv);
 glutInitDisplayMode(GLUT_SINGLE | GLUT_RGB);
 glutInitWindowSize(400, 400);
 glutInitWindowPosition(100, 200);
 glutCreateWindow("Our first GLUT application!");
 glutDisplayFunc(Display);
 Initialize();
 glutMainLoop();
 return 0;
}﻿
