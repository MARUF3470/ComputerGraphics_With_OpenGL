# ComputerGraphics_With_OpenGL

<h3>Full Code</h3>
#include<windows.h>
#include <GL/glut.h>
#include <cmath>
#define FILL true
#define NOT_FILL false

float xPos = 0.0f;
float yPos = 0.0f;
float angle = 0.0f;
float a=0.301;
float b=0.741;
float c=0.952;
float d=1.0;
float e=1.0;
float f=0.0;
float p=1.0;
float l=1.0;
float m=1.0;
float o=1.0;
float k=0.0;
float n=1.0;

//cicle formula & condition
<br/>
void makeCircle(float r, double x_center, double y_center,bool isFill)
{
    float deg = 0;
    double theta, x, y;

    glPointSize(3);

    if(isFill)
    {
        glBegin(GL_TRIANGLE_FAN);
    }
    else
    {
        glBegin(GL_POINTS);
    }

    while(deg < 360)
    {

        theta = (deg*M_PI)/180;
        x = x_center + r*cos(theta);
        y = y_center + r*sin(theta);


        glVertex2d(x, y);
        deg+=1;
    }
    glEnd();
}

void display()
{
    glClear(GL_COLOR_BUFFER_BIT);

    //Road
    glBegin(GL_QUADS);
    glColor3f(0.196, 0.192, 0.211);
    glVertex2f(0.0f, 0.0);
    glVertex2f(1.0f,0.0);
    glVertex2f(1.0f, 0.10f);
    glVertex2f(0.0f, 0.10f);
    glEnd();
    //Field
    glBegin(GL_QUADS);
    glColor3f(0.0, 0.427, 0.0);
    glVertex2f(1.0f, 0.10f);
    glVertex2f(0.0f, 0.10f);
    glVertex2f(0.0f, 0.4f);
    glVertex2f(1.0f, 0.4f);
    glEnd();
    //River
    glBegin(GL_QUADS);
    glColor3f(0.4, 0.7, 1.0);
    glVertex2f(0.0f, 0.4f);
    glVertex2f(1.0f, 0.4f);
    glVertex2f(1.0f, 0.6f);
    glVertex2f(0.0f, 0.6f);
    glEnd();
    //SKY
    glBegin(GL_QUADS);
    glColor3f(a, b, c);
    glVertex2f(1.0f, 0.6f);
    glVertex2f(0.0f, 0.6f);
    glVertex2f(0.0f, 1.0f);
    glVertex2f(1.0f, 1.0f);
    glEnd();

    //RiverLine
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.0f,0.60f);
    glVertex2f(1.0f,0.60f);
    glEnd();
    //Sun
    glColor3f(d, e, f);
    makeCircle(0.05,0.80,0.75,FILL);

    //cloud circle-1
    glColor3f(p, l, m);
    makeCircle(0.04,0.40,0.90,FILL);

    //cloud circle-2
    glColor3f(p, l, m);
    makeCircle(0.04,0.44,0.90,FILL);

    //cloud circle-3
    glColor3f(p, l, m);
    makeCircle(0.04,0.48,0.90,FILL);

    //cloud circle-4
    glColor3f(p, l, m);
    makeCircle(0.04,0.70,0.84,FILL);

    //cloud circle-5
    glColor3f(p, l, m);
    makeCircle(0.04,0.74,0.84,FILL);

    //Ghuri
    glBegin(GL_QUADS);
    glColor3f(o, k, n);
    glVertex2f(0.40f, 0.80f);
    glVertex2f(0.36f,0.76f);
    glVertex2f(0.40f, 0.72f);
    glVertex2f(0.44f, 0.76f);
    glEnd();

    //Ghuri Horizontal Line
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.36f,0.76f);
    glVertex2f(0.44f, 0.76f);
    glEnd();

    //Ghuri Vertical Line
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.40f, 0.80f);
    glVertex2f(0.40f, 0.72f);
    glEnd();

    //Mountains LEFT TO RIGHT
    glBegin(GL_TRIANGLES);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.20f, 0.60f);
    glVertex2f(0.30f, 0.68f);
    glVertex2f(0.38f, 0.60f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.37f, 0.60f);
    glVertex2f(0.5f, 0.72f);
    glVertex2f(0.58f, 0.60f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.5f, 0.6f);
    glVertex2f(0.6f, 0.7f);
    glVertex2f(0.7f, 0.60f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.6f, 0.6f);
    glVertex2f(0.7f, 0.72f);
    glVertex2f(0.8f, 0.60f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.8f, 0.6f);
    glVertex2f(0.88f, 0.68f);
    glVertex2f(0.96f, 0.6f);
    glEnd();

    //building-1
    glBegin(GL_QUADS);
    glColor3f(1.0, 0.0, 1.0);
    glVertex2f(0.02f, 0.60f);
    glVertex2f(0.08f,0.60f);
    glVertex2f(0.08f, 0.70f);
    glVertex2f(0.02f, 0.70f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.08f, 0.70f);
    glVertex2f(0.08f,0.60f);
    glVertex2f(0.10f, 0.60f);
    glVertex2f(0.10f, 0.72f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.02f, 0.70f);
    glVertex2f(0.08f,0.70f);
    glVertex2f(0.10f, 0.72f);
    glVertex2f(0.04f, 0.72f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.04f, 0.68f);
    glVertex2f(0.04f,0.66f);
    glVertex2f(0.06f, 0.66f);
    glVertex2f(0.06f, 0.68f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.04f, 0.64f);
    glVertex2f(0.04f,0.62f);
    glVertex2f(0.06f, 0.62f);
    glVertex2f(0.06f, 0.64f);
    glEnd();

    //building-2
    glBegin(GL_QUADS);
    glColor3f(1.0, 0.2, 0.2);
    glVertex2f(0.12f, 0.74f);
    glVertex2f(0.12f,0.60f);
    glVertex2f(0.18f, 0.60f);
    glVertex2f(0.18f, 0.74f);
    glEnd();
    glBegin(GL_QUADS);
    glColor3f(1.0, 0.6, 0.2);
    glVertex2f(0.18f, 0.74f);
    glVertex2f(0.18f,0.60f);
    glVertex2f(0.20f, 0.60f);
    glVertex2f(0.20f, 0.76f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 0.6, 0.2);
    glVertex2f(0.12f, 0.74f);
    glVertex2f(0.18f,0.74f);
    glVertex2f(0.20f, 0.76f);
    glVertex2f(0.14f, 0.76f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.14f, 0.72f);
    glVertex2f(0.14f,0.70f);
    glVertex2f(0.16f, 0.70f);
    glVertex2f(0.16f, 0.72f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 1.0, 0.4);
    glVertex2f(0.14f, 0.64f);
    glVertex2f(0.14f,0.62f);
    glVertex2f(0.16f, 0.62f);
    glVertex2f(0.16f, 0.64f);
    glEnd();

    //House-tree
    glBegin(GL_QUADS);
    glColor3f(0.6, 0.3, 0.0);
    glVertex2f(0.04f, 0.22f);
    glVertex2f(0.04,0.30);
    glVertex2f(0.06f, 0.30f);
    glVertex2f(0.06f, 0.22f);
    glEnd();

    //house tree Triangle-01
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.8, 0.0);
    glVertex2f(0.0f, 0.30f);
    glVertex2f(0.10f, 0.30f);
    glVertex2f(0.055f, 0.34f);
    glEnd();

    //house tree Triangle-02
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.8, 0.0);
    glVertex2f(0.0f, 0.32f);
    glVertex2f(0.10f, 0.32f);
    glVertex2f(0.055f, 0.36f);
    glEnd();

    //house tree Triangle-03
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.8, 0.0);
    glVertex2f(0.0f, 0.34f);
    glVertex2f(0.10f, 0.34f);
    glVertex2f(0.055f, 0.38f);
    glEnd();

    //tree-2
    glBegin(GL_QUADS);
    glColor3f(0.6, 0.3, 0.0);
    glVertex2f(0.12f, 0.42f);
    glVertex2f(0.12f,0.36f);
    glVertex2f(0.14f, 0.36f);
    glVertex2f(0.14f, 0.42f);
    glEnd();
    //tree Triangle-01
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.8, 0.0);
    glVertex2f(0.10f, 0.42f);
    glVertex2f(0.16f, 0.42f);
    glVertex2f(0.13f, 0.46f);
    glEnd();

    //tree Triangle-02
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.8, 0.0);
    glVertex2f(0.10f, 0.44f);
    glVertex2f(0.16f, 0.44f);
    glVertex2f(0.13f, 0.48f);
    glEnd();

    //house-body
    glBegin(GL_QUADS);
    glColor3f(0.752, 0.498, 0.0);
    glVertex2f(0.12f, 0.22f);
    glVertex2f(0.40,0.22);
    glVertex2f(0.40f, 0.30f);
    glVertex2f(0.12f, 0.30f);
    glEnd();

    //house-bodyLine
    glBegin(GL_LINES);
    glColor3f(0.0f,0.0f,0.0f);
    glVertex2f(0.20f, 0.22f);
    glVertex2f(0.20f,0.30f);
    glEnd();

    //House Shade
    glBegin(GL_QUADS);
    glColor3f(0.403, 0.219, 0.0);
    glVertex2f(0.40f, 0.30f);
    glVertex2f(0.36f,0.36f);
    glVertex2f(0.16f, 0.36f);
    glVertex2f(0.20f, 0.30f);
    glEnd();

    //House Shade -02
    glBegin(GL_TRIANGLES);
    glColor3f(0.721, 0.384, 0.105);
    glVertex2f(0.12f, 0.30f);
    glVertex2f(0.20f, 0.30f);
    glVertex2f(0.16f, 0.36f);
    glEnd();

    //House Door
    glBegin(GL_QUADS);
    glColor3f(0.298, 0.239, 0.239);
    glVertex2f(0.32f, 0.22f);
    glVertex2f(0.32,0.26);
    glVertex2f(0.26f, 0.26f);
    glVertex2f(0.26f, 0.22f);
    glEnd();

    //House Window
    glBegin(GL_QUADS);
    glColor3f(0.298, 0.239, 0.239);
    glVertex2f(0.18f, 0.24f);
    glVertex2f(0.18,0.28);
    glVertex2f(0.14f, 0.28f);
    glVertex2f(0.14f, 0.24f);
    glEnd();

    //plane
    glPushMatrix();
    glTranslatef(xPos, 0.0f, 0.0f  );

    glBegin(GL_QUADS);
    glColor3f(1.0, 0.0, 1.0);
    glVertex2f(0.10f, 0.86f);
    glVertex2f(0.22f,0.86f);
    glVertex2f(0.22f, 0.90f);
    glVertex2f(0.10f, 0.90f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.0, 0.8);
    glVertex2f(0.22f, 0.86f);
    glVertex2f(0.28f, 0.86f);
    glVertex2f(0.22f, 0.90f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 0.0, 0.0);
    glVertex2f(0.02f, 0.90f);
    glVertex2f(0.10f,0.86f);
    glVertex2f(0.10f, 0.90f);
    glVertex2f(0.04f, 0.93f);
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 0.6, 0.6);
    glVertex2f(0.10f, 0.82f);
    glVertex2f(0.14f,0.82f);
    glVertex2f(0.18f, 0.86f);
    glVertex2f(0.14f, 0.86f );
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(1.0, 0.6, 0.6);
    glVertex2f(0.14f, 0.90f );
    glVertex2f(0.18f,0.90f );
    glVertex2f(0.14f, 0.94f);
    glVertex2f(0.10f, 0.94f );
    glEnd();

    glPopMatrix();

    //hill-tree-1
    glBegin(GL_QUADS);
    glColor3f(0.6, 0.3, 0.0);
    glVertex2f(0.96f, 0.60f );
    glVertex2f(0.98f,0.60f );
    glVertex2f(0.98f, 0.66f);
    glVertex2f(0.96f, 0.66f );
    glEnd();

    //tree Triangle-01
    glBegin(GL_TRIANGLES);
    glColor3f(0.0, 0.4, 0.0);
    glVertex2f(0.94f, 0.66f );
    glVertex2f(1.0f, 0.66f );
    glVertex2f(0.97f, 0.72f );
    glEnd();

    //tree Triangle-02
    glBegin(GL_TRIANGLES);
    glColor3f(0.0, 0.4, 0.0);
    glVertex2f(0.94f, 0.69f );
    glVertex2f(1.0f, 0.69f );
    glVertex2f(0.97f, 0.76f );
    glEnd();

    //stand-tree-2
    glBegin(GL_QUADS);
    glColor3f(0.6, 0.3, 0.0);
    glVertex2f(0.74f, 0.44f );
    glVertex2f(0.74f,0.38f );
    glVertex2f(0.76f, 0.38f);
    glVertex2f(0.76f, 0.44f );
    glEnd();

    //tree Triangle-01
    glBegin(GL_TRIANGLES);
    glColor3f(0.0, 0.4, 0.0);
    glVertex2f(0.70f, 0.44f );
    glVertex2f(0.80f, 0.44f );
    glVertex2f(0.75f, 0.50f );
    glEnd();

    //Moving BOAT

    glPushMatrix();
    glTranslatef(xPos, 0.0f, 0.0f);

    glBegin(GL_POLYGON);
    glColor3f(0.286, 0.219, 0.09);
    glVertex2f(0.06f, 0.52f );
    glVertex2f(0.1f, 0.48f );
    glVertex2f(0.22f, 0.48f );
    glVertex2f(0.26f, 0.52f );
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(0.831, 0.713, 0.454);
    glVertex2f(0.12f, 0.52f );
    glVertex2f(0.12f, 0.54f );
    glVertex2f(0.2f, 0.54f );
    glVertex2f(0.2f, 0.52f );
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.866, 0.486, 0.168);
    glVertex2f(0.24f, 0.52f );
    glVertex2f(0.22f, 0.58f );
    glVertex2f(0.28f, 0.56f );
    glEnd();

    glBegin(GL_LINES);
    glColor3f(1.0, 1.0, 1.0);
    glVertex2f(0.24f, 0.52f );
    glVertex2f(0.25f, 0.566f );
    glEnd();

    glPopMatrix();

    //BOAT
    glBegin(GL_POLYGON);
    glColor3f(0.286, 0.219, 0.09);
    glVertex2f(0.48f, 0.44f );
    glVertex2f(0.64f, 0.44f );
    glVertex2f(0.6f, 0.4f );
    glVertex2f(0.52f, 0.4f );
    glEnd();

    glBegin(GL_QUADS);
    glColor3f(0.831, 0.713, 0.454);
    glVertex2f(0.52f, 0.44f );
    glVertex2f(0.52f, 0.46f );
    glVertex2f(0.6f, 0.46f );
    glVertex2f(0.6f, 0.44f );
    glEnd();

    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.46f, 0.50f );
    glVertex2f(0.46f, 0.38f );
    glEnd();

    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.48f, 0.44f );
    glVertex2f(0.46f, 0.44f );
    glEnd();

    //Road line 1
    glBegin(GL_LINES);
    glColor3f(1.0f,1.0f,1.0f);
    glVertex2f(0.0f,0.06f);
    glVertex2f(0.10f,0.06f);
    glEnd();

    //Road line 2
    glBegin(GL_LINES);
    glColor3f(1.0f,1.0f,1.0f);
    glVertex2f(0.20f,0.06f);
    glVertex2f(0.30f,0.06f);
    glEnd();

    //Road line 3
    glBegin(GL_LINES);
    glColor3f(1.0f,1.0f,1.0f);
    glVertex2f(0.40f,0.06f);
    glVertex2f(0.50f,0.06f);
    glEnd();

    //Road line 4
    glBegin(GL_LINES);
    glColor3f(1.0f,1.0f,1.0f);
    glVertex2f(0.60f,0.06f);
    glVertex2f(0.700f,0.06f);
    glEnd();

    //Road line 5
    glBegin(GL_LINES);
    glColor3f(1.0f,1.0f,1.0f);
    glVertex2f(0.80f,0.06f);
    glVertex2f(0.900f,0.06f);
    glEnd();

    //bus Body

    glPushMatrix();
    glTranslatef(xPos , 0.0f, 0.0f );

    glBegin(GL_QUADS);
    glColor3f(0.831, 0.713, 0.454);
    glVertex2f(0.06f, 0.14f );
    glVertex2f(0.06f, 0.06f );
    glVertex2f(0.34f, 0.06f );
    glVertex2f(0.30f, 0.14f );
    glEnd();

    //bus wheel-1
    glColor3f(0.0, 0.0, 0.0);
    makeCircle(0.02,0.10,0.06,FILL);

    //bus wheel-1 Center
    glColor3f(1.0, 1.0, 1.0);
    makeCircle(0.01,0.10,0.06,FILL);

    //bus wheel-2
    glColor3f(0.0, 0.0, 0.0);
    makeCircle(0.02,0.15,0.06,FILL);

    //bus wheel-2 Center
    glColor3f(1.0, 1.0, 1.0);
    makeCircle(0.01,0.15,0.06,FILL);

    //bus wheel-3
    glColor3f(0.0, 0.0, 0.0);
    makeCircle(0.02,0.28,0.06,FILL);

    //bus wheel-3 Center
    glColor3f(1.0, 1.0, 1.0);
    makeCircle(0.01,0.28,0.06,FILL);

    //bus Body - windows
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.3, 0.1);
    glVertex2f(0.06f, 0.14f );
    glVertex2f(0.10f, 0.14f );
    glVertex2f(0.10f, 0.10f );
    glVertex2f(0.06f, 0.10f );
    glEnd();

    //bus Body - windows
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.3, 0.1);
    glVertex2f(0.10f, 0.14f );
    glVertex2f(0.14f, 0.14f );
    glVertex2f(0.14f, 0.10f );
    glVertex2f(0.10f, 0.10f );
    glEnd();

    //bus Body - windows
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.3, 0.1);
    glVertex2f(0.14f, 0.14f );
    glVertex2f(0.18f, 0.14f );
    glVertex2f(0.18f, 0.10f );
    glVertex2f(0.14f, 0.10f );
    glEnd();

    //bus Body - windows Driver
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.3, 0.1);
    glVertex2f(0.26f, 0.14f );
    glVertex2f(0.30f, 0.14f );
    glVertex2f(0.30f, 0.10f );
    glVertex2f(0.26f, 0.10f );
    glEnd();

    //Bus Body - Front Glass
    glBegin(GL_TRIANGLES);
    glColor3f(0.4, 0.7, 1.0);
    glVertex2f(0.3f, 0.14f );
    glVertex2f(0.30f, 0.10f );
    glVertex2f(0.32f, 0.10f );
    glEnd();

    //Line 1
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.1f,0.14f);
    glVertex2f(0.1f,0.1f);
    glEnd();

    //Line 2
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.14f,0.14f);
    glVertex2f(0.14f,0.1f);
    glEnd();

    glPopMatrix();

    //House 2 body
    glBegin(GL_QUADS);
    glColor3f(0.7, 0.4, 1.0);
    glVertex2f(0.50f, 0.22f );
    glVertex2f(0.50f, 0.30f );
    glVertex2f(0.70f, 0.30f );
    glVertex2f(0.70f, 0.22f );
    glEnd();

    //House 2 Shade
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.0, 0.1);
    glVertex2f(0.50f, 0.30f );
    glVertex2f(0.70f, 0.30f );
    glVertex2f(0.70f, 0.36f );
    glVertex2f(0.50f, 0.36f );
    glEnd();

    //House 2 upper shade
    glBegin(GL_QUADS);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.66f, 0.36f );
    glVertex2f(0.70f, 0.36f );
    glVertex2f(0.70f, 0.38f );
    glVertex2f(0.66f, 0.38f );
    glEnd();

    //house 2 door
    glBegin(GL_QUADS);
    glColor3f(0.2, 0.3, 0.4);
    glVertex2f(0.58f, 0.22f );
    glVertex2f(0.58f, 0.28f );
    glVertex2f(0.62f, 0.28f );
    glVertex2f(0.62f, 0.22f );
    glEnd();

    //cicle tree
    glBegin(GL_QUADS);
    glColor3f(0.6, 0.3, 0.0);
    glVertex2f(0.80f, 0.20f );
    glVertex2f(0.82f, 0.20f );
    glVertex2f(0.83f, 0.30f );
    glVertex2f(0.79f, 0.30f );
    glEnd();

    //tree circle-1
    glColor3f(0.0, 0.2, 0.0);
    makeCircle(0.04,0.79,0.30,FILL);

    //tree circle-2
    glColor3f(0.0, 0.2, 0.0);
    makeCircle(0.04,0.82,0.30,FILL);

    //tree circle-3
    glColor3f(0.0, 0.2, 0.0);
    makeCircle(0.04,0.81,0.32,FILL);

    //fench line-1
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.42f,0.32f);
    glVertex2f(0.42f,0.24f);
    glEnd();

    //fench line-2
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.43f,0.32f);
    glVertex2f(0.43f,0.24f);
    glEnd();

    //fench line-3
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.44f,0.32f);
    glVertex2f(0.44f,0.24f);
    glEnd();

    //fench line-4
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.45f,0.32f);
    glVertex2f(0.45f,0.24f);
    glEnd();

    //fench line-5
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.46f,0.32f);
    glVertex2f(0.46f,0.24f);
    glEnd();

    //fench line-6
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.47f,0.32f);
    glVertex2f(0.47f,0.24f);
    glEnd();

    //fench line-7
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.48f,0.32f);
    glVertex2f(0.48f,0.24f);
    glEnd();

    //fench line-8
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.40f,0.30f);
    glVertex2f(0.50f,0.30f);
    glEnd();

    //fench line-9
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.40f,0.28f);
    glVertex2f(0.50f,0.28f);
    glEnd();

    //fench line-10
    glBegin(GL_LINES);
    glColor3f(0.0, 0.0, 0.0);
    glVertex2f(0.40f,0.26f);
    glVertex2f(0.50f,0.26f);
    glEnd();


    glutSwapBuffers();
}






void update(int value)
{
    xPos += 0.01f;

    if (xPos>1)
    {
        xPos = 0-xPos;
    }

    glutPostRedisplay();
    glutTimerFunc(100, update, 0);
}


int main(int argc, char **argv)
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB);
    glutInitWindowSize(600, 600);
    glutCreateWindow("OUR CITY");
    glClearColor(1.0f, 1.0f, 1.0f, 1.0f);  // White background
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(0.0f, 1.0f, 0.0f, 1.0f);
    glMatrixMode(GL_MODELVIEW);
    glutDisplayFunc(display);
    glutTimerFunc(100, update, 0);
    glutMainLoop();
    return 0;
}
