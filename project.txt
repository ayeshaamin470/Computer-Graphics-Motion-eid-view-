#include<cstdio>
#include <iostream>
using namespace std;
#include<stdio.h>
#include<stdlib.h>
#include<GL/gl.h>
#include<GL/glut.h>
#include<math.h>
#include<windows.h>
#include<MMsystem.h>



float _cloudmove1 = 0.0;
float _cloudmove2 = 0.0;
float _cloudmove3 = 0.0;
float _cloudmove4 = 0.0;
float _cloudmove5 = 0.0;
float _cloudmove6 = 0.0;
float _cloudmove7 = 0.0;
float _cloudmove8 = 0.0;
float _cloudmove9 = 0.0;
float _carmove1 = 0.0;
float _carmove2 = 0.0;
float _heli = 0.0;
int nview=0;
bool rainday = false;
bool move1 = true;
bool move2 = true;
float _nt = 0.0;
bool night = false;
float _rain = 0.0;
int n = 0;
char text[] = "SLOW";
char text2[] = "EID MUBARAK";
void slow( float x, float y, char *st)
{
    int l,i;


    l=strlen( st ); // see how many characters are in text string.
    glColor3f(1.0,1.0,1.0);

    glRasterPos2f( x, y); // location to start printing text
    for( i=0; i < l; i++) // loop until i is greater then l
    {
       glutBitmapCharacter(GLUT_BITMAP_HELVETICA_12, st[i]);

    }
}
void eidmubarak( float x, float y, char *st)
{
    int l,i;


    l=strlen( st ); // see how many characters are in text string.
    glColor3ub(147, 27, 239);

    glRasterPos2f( x, y); // location to start printing text
    for( i=0; i < l; i++) // loop until i is greater then l
    {
       glutBitmapCharacter(GLUT_BITMAP_TIMES_ROMAN_24, st[i]);

    }
}

void myDisplay(void)
{

float x,y,i;
glClear (GL_COLOR_BUFFER_BIT);

glPointSize(5.0);
if(nview==0){

float x,y,i;
glClear (GL_COLOR_BUFFER_BIT);

glPointSize(5.0);
glBegin(GL_QUADS);
    //glColor3ub(0,0,128);
    glColor3ub(135, 206, 250);
    glVertex2f(-100, 720);
	glVertex2f(1280, 720);
    //glColor3ub(135, 206, 250);
    glColor3ub(0,0,128);
	glVertex2f(1280, 0);
	glVertex2f(-100, 0);
	glEnd();
	//field
	glBegin(GL_QUADS);

    glColor3ub(46,139,87);
    glVertex2f(-100, 250);
	glVertex2f(1280, 250);

    glColor3ub(32, 226, 58);
	glVertex2f(1280, 0);
	glVertex2f(-100, 0);
	glEnd();


       glBegin(GL_TRIANGLE_FAN); //sun1
		glColor3ub(255,246,127);
				//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=30+65*sin(i);
			y=588+60*cos(i);
			glVertex2f(x,y);
		}
       glEnd();

	glBegin(GL_TRIANGLE_FAN); //SUN3
	glColor3ub(255,230,47);
	//glColor3ub(255,215,0);

		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=30+40*sin(i);
			y=588+35*cos(i);
			glVertex2f(x,y);
		}
glEnd();

glPushMatrix();
glTranslated(_cloudmove1,0,0);
glPushMatrix();
glTranslated(0,100,0);
	glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=340+50*sin(i);
			y=460+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 2
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=420+50*sin(i);
			y=460+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 3
		glColor3ub(176, 196 ,222);//gray
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=500+50*sin(i);
			y=480+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 4
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=470+40*sin(i);
			y=530+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 5
		//glColor3ub(220, 220 ,220);
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=570+50*sin(i);
			y=480+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 6
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=610+30*sin(i);
			y=460+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //GRAY CLOUDS 7
		glColor3ub(176, 196 ,222);
		//glColor3ub(	176,196,245);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=640+30*sin(i);
			y=440+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


   glBegin(GL_QUADS);//WHITE QUARD
 	glColor3ub(255 ,250, 250);
    glVertex2f(0, 410);
	glVertex2f(290, 410);
	glVertex2f(290, 440);
	glVertex2f(0, 440);
	glEnd();
	glBegin(GL_QUADS);//GRAY QUARD
glColor3ub(176, 196 ,222);

 	//glColor3ub(	176,196,245);
    glVertex2f(290, 410);
	glVertex2f(640, 410);
	glVertex2f(640, 450);
	glVertex2f(290, 450);
	glEnd();



//WHITE clouds start

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=30+30*sin(i);
			y=440+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN); //cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=90+45*sin(i);
			y=450+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud3
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=170+60*sin(i);
			y=480+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //mix1
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=250+50*sin(i);
			y=460+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN); //cloud4
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=310+60*sin(i);
			y=510+60*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN); //cloud5
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=390+60*sin(i);
			y=550+60*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud6
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=420+45*sin(i);
			y=510+45*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud MIX
		glColor3ub(250 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=300+30*sin(i);
			y=440+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
//small cloud start
glPopMatrix();
glPushMatrix();
glTranslated(_cloudmove2,0,0);
glPushMatrix();
glTranslated(0,50,0);
glBegin(GL_TRIANGLE_FAN); //small cloud1
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=600+20*sin(i);
			y=270+20*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=630+20*sin(i);
			y=275+20*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud3
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=660+25*sin(i);
			y=285+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud4
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=700+35*sin(i);
			y=290+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud5
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=740+20*sin(i);
			y=270+20*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud6
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=790+40*sin(i);
			y=300+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud7
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=835+25*sin(i);
			y=275+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_QUADS);//small WHITE QUARD
 	glColor3ub(255 ,250, 250);
    glVertex2f(600, 250);
	glVertex2f(840, 250);
	glVertex2f(840, 270);
	glVertex2f(600, 270);
	glEnd();
glPopMatrix();
//small stars 2
glPopMatrix();
glPushMatrix();
glTranslated(_cloudmove3,0,0);
glBegin(GL_TRIANGLE_FAN); //small cloud3
		//glColor3ub(255 ,250, 250);
		glColor3ub(176, 196 ,222);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1070+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //small cloud4
		//glColor3ub(255 ,250, 250);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1100+25*sin(i);
			y=545+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //small cloud5
		//glColor3ub(255 ,250, 250);
	glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1150+45*sin(i);
			y=555+45*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud6 gray
		//glColor3ub(255 ,250, 250);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1190+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN); //small cloud1
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1000+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1054+40*sin(i);
			y=560+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();



	glBegin(GL_QUADS);//small gray QUARD 2
 	glColor3ub(226,237,240);
    glVertex2f(1070, 510);
	glVertex2f(1185, 510);
	glVertex2f(1185, 530);
	glVertex2f(1070, 530);
	glEnd();
	glBegin(GL_QUADS);//small WHITE QUARD 2
 	glColor3ub(255 ,250, 250);
    glVertex2f(1000, 510);
	glVertex2f(1080, 510);
	glVertex2f(1080, 530);
	glVertex2f(1000, 530);
	glEnd();
	glBegin(GL_TRIANGLE_FAN); //small cloud6 mix
		glColor3ub(255 ,250, 250);
		//glColor3ub(176, 196 ,222);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1080+20*sin(i);
			y=530+20*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN); //small cloud4
		glColor3ub(239,247,249);
        for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1200+30*sin(i);
			y=360+30*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud3
		glColor3ub(239,247,249);
        for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1100+30*sin(i);
			y=360+30*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
        glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1154+40*sin(i);
			y=360+40*cos(i);
			glVertex2f(x,y);
		}
glEnd();
glPopMatrix();
glPopMatrix();
//Building
glBegin(GL_QUADS); //1
glColor3ub(240,255,255);
glVertex2i(-100, 450);
glVertex2i(-10, 450);
glVertex2i(-10, 250);
glVertex2i(-100, 250);
glEnd();
glBegin(GL_QUADS); //2
glColor3ub(250,128,114);
glVertex2i(140, 420);
glVertex2i(30, 420);
glVertex2i(30, 250);
glVertex2i(140, 250);
glEnd();


glBegin(GL_QUADS); //4
glColor3ub	(255,215,0);
glVertex2i(300, 400);
glVertex2i(190, 400);
glVertex2i(190, 250);
glVertex2i(300, 250);
glEnd();

glBegin(GL_QUADS); //5
glColor3ub	(245,245,245);
glVertex2i(320, 430);
glVertex2i(410, 430);
glVertex2i(410, 250);
glVertex2i(320, 250);
glEnd();
glBegin(GL_QUADS); //6
glColor3ub	(255,222,150);
glVertex2i(500, 400);
glVertex2i(550, 400);
glVertex2i(550, 250);
glVertex2i(500, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(255,215,0);
glVertex2i(630, 360);
glVertex2i(690, 360);
glVertex2i(690, 250);
glVertex2i(600, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(85,107,47);
glVertex2i(790, 360);
glVertex2i(720, 360);
glVertex2i(720, 250);
glVertex2i(790, 250);
glEnd();
glBegin(GL_QUADS); //10
glColor3ub(246,193,228);
glVertex2i(1280, 390);
glVertex2i(1200, 390);
glVertex2i(1200, 250);
glVertex2i(1280, 250);
glEnd();
glBegin(GL_QUADS); //9
glColor3ub	(220,219,255);
glVertex2i(1180, 370);
glVertex2i(1100, 370);
glVertex2i(1100, 250);
glColor3ub(176,196,222);
glVertex2i(1180, 250);
glEnd();

glBegin(GL_QUADS); //s1
glColor3ub	(176,196,222);
glVertex2i(-80, 370);
glVertex2i(90, 370);
glVertex2i(90, 250);
glVertex2i(-80, 250);
glEnd();

glBegin(GL_QUADS); //s2
glColor3ub(176,196,222);
glVertex2i(310, 350);
glVertex2i(370, 350);
glVertex2i(370, 250);
glVertex2i(310, 250);
glEnd();

// trees

glBegin(GL_QUADS); //tree1
glColor3ub(139,69,19);
glVertex2i(400, 350);
glVertex2i(430, 350);
glVertex2i(430, 250);
glVertex2i(400, 250);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(415, 350);
glVertex2i(350, 280);
glVertex2i(480, 280);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(415, 400);
glVertex2i(350, 310);
glVertex2i(480, 310);
glEnd();
glBegin(GL_QUADS); //tree2
glColor3ub(139,69,19);
glVertex2i(-15, 350);
glVertex2i(10, 350);
glVertex2i(10, 250);
glVertex2i(-15, 250);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(0, 350);
glVertex2i(-65, 280);
glVertex2i(65, 280);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(0, 400);
glVertex2i(-65, 310);
glVertex2i(65, 310);
glEnd();
glBegin(GL_QUADS); //tree3
glColor3ub(139,69,19);
glVertex2i(183, 350);
glVertex2i(212, 350);
glVertex2i(212, 250);

glColor3ub(128,0,0);

glVertex2i(183, 250);
glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(60,179,113);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=193+50*sin(i);
			y=340+55*cos(i);
			glVertex2f(x,y);
		}
	glEnd();
//treeend


}
else{

    float x,y,i;
glClear (GL_COLOR_BUFFER_BIT);
glPointSize(5.0);

  glBegin(GL_QUADS);
   glColor3ub(0,0,28);
   glVertex2f(-100, 720);
   glVertex2f(1280, 720);
  // glColor3ub(0,0,28);
glColor3ub(10,21,68);
   glVertex2f(1280, 0);
  // glColor3ub(70,130,180);
   glVertex2f(-100, 0);
   glEnd();

   //field
	glBegin(GL_QUADS);

    glColor3ub(46,139,87);
    glVertex2f(-100, 250);
	glVertex2f(1280, 250);

    glColor3ub(32, 226, 58);
	glVertex2f(1280, 0);
	glVertex2f(-100, 0);
	glEnd();


		glBegin(GL_TRIANGLE_FAN);//moon1
		glColor3ub(255,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=220+55*sin(i);
			y=490+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_POLYGON);//moon2
	     glColor3ub(0,0,40);
         //glColor3ub(25,25,112);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=240+54*sin(i);
			y=507+39*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 if(n>9){//loop for starrs   ///m here yeah got it. kotha shesh hole call diyo
		 glBegin(GL_TRIANGLE_FAN);//starts start
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=420+5.3*sin(i);
			y=320+5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		//new

        glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=20+4.5*sin(i);
			y=265+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=20+2.5*sin(i);
			y=645+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-60+2.5*sin(i);
			y=465+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-50+2*sin(i);
			y=405+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1150+1.5*sin(i);
			y=405+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1120+4.5*sin(i);
			y=305+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1120+4.5*sin(i);
			y=305+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=750+1.5*sin(i);
			y=405+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1050+1.5*sin(i);
			y=525+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-60+2.5*sin(i);
			y=665+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=80+1.5*sin(i);
			y=655+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=780+1.5*sin(i);
			y=605+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=150+4.5*sin(i);
			y=465+4.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=120+5*sin(i);
			y=365+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=320+5*sin(i);
			y=405+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=100+3*sin(i);
			y=405+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

        glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1000+4*sin(i);
			y=405+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1120+2*sin(i);
			y=425+1.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
	  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=720+3*sin(i);
			y=525+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=820+5*sin(i);
			y=625+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=490+5*sin(i);
			y=425+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
        	  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=720+5*sin(i);
			y=385+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1120+5*sin(i);
			y=700+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1120+5*sin(i);
			y=425+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=320+3*sin(i);
			y=225+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			  glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=320+4*sin(i);
			y=565+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		 }
		 else{
		glBegin(GL_TRIANGLE_FAN);//small start
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=480+3*sin(i);
			y=370+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=40+3*sin(i);
			y=655+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-50+1.5*sin(i);
			y=585+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

         glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1010+5*sin(i);
			y=555+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=810+2*sin(i);
			y=505+1.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=960+4*sin(i);
			y=305+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=910+4*sin(i);
			y=418+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=40+4*sin(i);
			y=505+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=20+3*sin(i);
			y=435+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=260+3*sin(i);
			y=635+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1000+2*sin(i);
			y=635+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=800+2*sin(i);
			y=535+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

 glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=500+3*sin(i);
			y=635+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		//endnew
			glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=760+5*sin(i);
			y=425+5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


		glBegin(GL_TRIANGLE_FAN);//small start
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=480+3*sin(i);
			y=370+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=490+3.5*sin(i);
			y=495+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=640+4*sin(i);
			y=445+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=700+3*sin(i);
			y=415+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=590+2.5*sin(i);
			y=365+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=690+1*sin(i);
			y=375+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=740+2*sin(i);
			y=325+2*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=440+2*sin(i);
			y=425+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=620+2*sin(i);
			y=425+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=700+3*sin(i);
			y=415+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=590+2.5*sin(i);
			y=365+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=690+1*sin(i);
			y=375+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=740+2*sin(i);
			y=325+2*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=440+2*sin(i);
			y=425+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=620+2*sin(i);
			y=545+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		//tv


		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=100+5*sin(i);
			y=350+5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-10+6*sin(i);
			y=380+6*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=20+2*sin(i);
			y=395+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=309+3*sin(i);
			y=515+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=130+1*sin(i);
			y=375+1*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-20+2*sin(i);
			y=325+2*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=240+2.5*sin(i);
			y=425+2.5*cos(i);
			glVertex2f(x,y);
		}

		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=40+2.5*sin(i);
			y=625+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=940+2.5*sin(i);
			y=625+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=240+2.5*sin(i);
			y=425+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1040+2*sin(i);
			y=675+1.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN);
		glColor3ub(224,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=70+2*sin(i);
			y=555+1*cos(i);
			glVertex2f(x,y);
		}
		 }
glEnd();
//field
	glBegin(GL_QUADS);

    glColor3ub(46,139,87);
    glVertex2f(-100, 250);
	glVertex2f(1280, 250);

    glColor3ub(32, 226, 58);
	glVertex2f(1280, 0);
	glVertex2f(-100, 0);
	glEnd();
		//clouds


		glPushMatrix();
    glTranslatef(_cloudmove4, 0.0, 0.0);
		glBegin(GL_TRIANGLE_FAN);   //cloud1 (set 1)

	  glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-90+48*sin(i);
			y=618+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud2
	 glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-30+48*sin(i);
			y=590+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud3
	    glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=20+48*sin(i);
			y=600+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud4
 	glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=80+48*sin(i);
			y=630+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud5
 		glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=-40+48*sin(i);
			y=650+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //cloud6

 		glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=28+48*sin(i);
			y=650+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

		glPopMatrix();
		glPushMatrix();
    glTranslatef(_cloudmove5, 0.0, 0.0);

		glBegin(GL_TRIANGLE_FAN);//cloud1 (set 2)

	    glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x= 208+48*sin(i);
			y=508+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


		glBegin(GL_TRIANGLE_FAN); //cloud2
	  glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=268+48*sin(i);
			y=480+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud3
	    glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=330+48*sin(i);
			y=490+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud4
 	glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=392+48*sin(i);
			y=520+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud5
 	// glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=266+48*sin(i);
			y=540+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //cloud6
 //glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=328+48*sin(i);
			y=540+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glPopMatrix();
		glPushMatrix();
    glTranslatef(_cloudmove6, 0.0, 0.0);


			glBegin(GL_TRIANGLE_FAN);//cloud1 (set 3)

	    glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x= 536+48*sin(i);
			y=618+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


		glBegin(GL_TRIANGLE_FAN); //cloud2
	   glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=596+48*sin(i);
			y=590+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud3
	     glColor3ub(192,214,228);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=656+48*sin(i);
			y=600+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud4
 	 glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=716+48*sin(i);
			y=630+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //cloud5
 	 glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=590+48*sin(i);
			y=650+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //cloud6
 	 glColor3ub(226,234,236);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=652+48*sin(i);
			y=650+48*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//day
glPopMatrix();
		glPushMatrix();
    glTranslatef(_cloudmove7, 0.0, 0.0);
		glBegin(GL_TRIANGLE_FAN); //small cloud3
		//glColor3ub(255 ,250, 250);
		glColor3ub(176, 196 ,222);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1070+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //small cloud4
		//glColor3ub(255 ,250, 250);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1100+25*sin(i);
			y=545+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
			glBegin(GL_TRIANGLE_FAN); //small cloud5
		//glColor3ub(255 ,250, 250);
	glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1150+45*sin(i);
			y=555+45*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud6 gray
		//glColor3ub(255 ,250, 250);
		glColor3ub(226,237,240);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1190+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN); //small cloud1
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1000+25*sin(i);
			y=535+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=1054+40*sin(i);
			y=560+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();



	glBegin(GL_QUADS);//small gray QUARD 2
 	glColor3ub(226,237,240);
    glVertex2f(1070, 510);
	glVertex2f(1185, 510);
	glVertex2f(1185, 530);
	glVertex2f(1070, 530);
	glEnd();
	glBegin(GL_QUADS);//small WHITE QUARD 2
 	glColor3ub(255 ,250, 250);
    glVertex2f(1000, 510);
	glVertex2f(1080, 510);
	glVertex2f(1080, 530);
	glVertex2f(1000, 530);
	glEnd();

	glPopMatrix();
		glPushMatrix();
    glTranslatef(_cloudmove8, 0.0, 0.0);



glBegin(GL_TRIANGLE_FAN); //small cloud1
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=800+25*sin(i);
			y=455+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=854+40*sin(i);
			y=480+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud3
		glColor3ub(255 ,250, 250);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=900+25*sin(i);
			y=455+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_QUADS);//small WHITE QUARD hex1
 	glColor3ub(255 ,250, 250);
    glVertex2f(800, 455);
	glVertex2f(900, 455);
	glVertex2f(900, 430);
	glVertex2f(800, 430);
	glEnd();

	glPopMatrix();
		glPushMatrix();
    glTranslatef(_cloudmove9, 0.0, 0.0);
glBegin(GL_TRIANGLE_FAN); //small cloud1
		glColor3ub(220,220,220);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=0+25*sin(i);
			y=405+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud2
		glColor3ub(220,220,220);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=44+40*sin(i);
			y=430+40*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_TRIANGLE_FAN); //small cloud3
		glColor3ub(220,220,220);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=90+25*sin(i);
			y=405+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_QUADS);//small WHITE QUARD hex1
 	glColor3ub(220,220,220);
    glVertex2f(0, 405);
	glVertex2f(90, 405);
	glVertex2f(90, 380);
	glVertex2f(0, 380);
	glEnd();
	glPopMatrix();




//Building
glBegin(GL_QUADS); //1
glColor3ub(240,255,255);
glVertex2i(-100, 450);
glVertex2i(-10, 450);
glVertex2i(-10, 250);
glVertex2i(-100, 250);
glEnd();
glBegin(GL_QUADS); //2
glColor3ub(250,128,114);
glVertex2i(140, 420);
glVertex2i(30, 420);
glVertex2i(30, 250);
glVertex2i(140, 250);
glEnd();


glBegin(GL_QUADS); //4
glColor3ub	(255,215,0);
glVertex2i(300, 400);
glVertex2i(190, 400);
glVertex2i(190, 250);
glVertex2i(300, 250);
glEnd();

glBegin(GL_QUADS); //5
glColor3ub	(245,245,245);
glVertex2i(320, 430);
glVertex2i(410, 430);
glVertex2i(410, 250);
glVertex2i(320, 250);
glEnd();
glBegin(GL_QUADS); //6
glColor3ub	(255,222,150);
glVertex2i(500, 400);
glVertex2i(550, 400);
glVertex2i(550, 250);
glVertex2i(500, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(255,215,0);
glVertex2i(630, 360);
glVertex2i(690, 360);
glVertex2i(690, 250);
glVertex2i(600, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(85,107,47);
glVertex2i(790, 360);
glVertex2i(720, 360);
glVertex2i(720, 250);
glVertex2i(790, 250);
glEnd();
glBegin(GL_QUADS); //10
glColor3ub(246,193,228);
glVertex2i(1280, 390);
glVertex2i(1200, 390);
glVertex2i(1200, 250);
glVertex2i(1280, 250);
glEnd();
glBegin(GL_QUADS); //9
glColor3ub	(220,219,255);
glVertex2i(1180, 370);
glVertex2i(1100, 370);
glVertex2i(1100, 250);
glColor3ub(176,196,222);
glVertex2i(1180, 250);
glEnd();

glBegin(GL_QUADS); //s1
glColor3ub	(176,196,222);
glVertex2i(-80, 370);
glVertex2i(90, 370);
glVertex2i(90, 250);
glVertex2i(-80, 250);
glEnd();

glBegin(GL_QUADS); //s2
glColor3ub(176,196,222);
glVertex2i(310, 350);
glVertex2i(370, 350);
glVertex2i(370, 250);
glVertex2i(310, 250);
glEnd();
//Building
glBegin(GL_QUADS); //1
glColor3ub(240,255,255);
glVertex2i(-100, 450);
glVertex2i(-10, 450);
glVertex2i(-10, 250);
glVertex2i(-100, 250);
glEnd();
glBegin(GL_QUADS); //1st building window1
glColor3ub	(240,230,140);
glVertex2i(-97, 430);
glVertex2i(-60, 430);
glVertex2i(-60, 390);
glVertex2i(-97, 390);
glEnd();
glBegin(GL_QUADS); //1st building window2
glColor3ub	(240,230,140);
glVertex2i(-50, 430);
glVertex2i(-13, 430);
glVertex2i(-13, 390);
glVertex2i(-50, 390);
glEnd();
glBegin(GL_QUADS); //2
glColor3ub(250,128,114);
glVertex2i(140, 420);
glVertex2i(30, 420);
glVertex2i(30, 250);
glVertex2i(140, 250);
glEnd();


glBegin(GL_QUADS); //4
glColor3ub	(255,215,0);
glVertex2i(300, 400);
glVertex2i(190, 400);
glVertex2i(190, 250);
glVertex2i(300, 250);
glEnd();
glBegin(GL_QUADS); //1st building window1
glColor3ub	(240,230,140);
glVertex2i(-97, 430);
glVertex2i(-60, 430);
glVertex2i(-60, 390);
glVertex2i(-97, 390);
glEnd();
glBegin(GL_QUADS); //1st building window2
glColor3ub	(240,230,140);
glVertex2i(-50, 430);
glVertex2i(-13, 430);
glVertex2i(-13, 390);
glVertex2i(-50, 390);
glEnd();
glBegin(GL_QUADS); //5
glColor3ub	(245,245,245);
glVertex2i(320, 430);
glVertex2i(410, 430);
glVertex2i(410, 250);
glVertex2i(320, 250);
glEnd();
glBegin(GL_QUADS); //5st building window1
glColor3ub	(240,230,140);
glVertex2i(326, 420);
glVertex2i(365, 420);
glVertex2i(365, 390);
glVertex2i(326, 390);
glEnd();
glBegin(GL_QUADS); //5st building window2
glColor3ub	(240,230,140);
glVertex2i(407, 420);
glVertex2i(370, 420);
glVertex2i(370, 390);
glVertex2i(407, 390);
glEnd();
glBegin(GL_QUADS); //5st building window1
glColor3ub	(240,230,140);
glVertex2i(326, 330);
glVertex2i(365, 330);
glVertex2i(365, 380);
glVertex2i(326, 380);
glEnd();
glBegin(GL_QUADS); //5st building window2
glColor3ub	(240,230,140);
glVertex2i(407, 330);
glVertex2i(370, 330);
glVertex2i(370, 380);
glVertex2i(407, 380);
glEnd();
glBegin(GL_QUADS); //6
glColor3ub	(255,222,150);
glVertex2i(500, 400);
glVertex2i(550, 400);
glVertex2i(550, 250);
glVertex2i(500, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(255,215,0);
glVertex2i(630, 360);
glVertex2i(690, 360);
glVertex2i(690, 250);
glVertex2i(600, 250);
glEnd();
glBegin(GL_QUADS); //8
glColor3ub	(85,107,47);
glVertex2i(790, 360);
glVertex2i(720, 360);
glVertex2i(720, 250);
glVertex2i(790, 250);
glEnd();
glBegin(GL_QUADS); //10
glColor3ub(246,193,228);
glVertex2i(1280, 390);
glVertex2i(1200, 390);
glVertex2i(1200, 250);
glVertex2i(1280, 250);
glEnd();
glBegin(GL_QUADS); //9
glColor3ub	(220,219,255);
glVertex2i(1180, 370);
glVertex2i(1100, 370);
glVertex2i(1100, 250);
glColor3ub(176,196,222);
glVertex2i(1180, 250);
glEnd();
glBegin(GL_QUADS); //5st building window1
glColor3ub	(240,230,140);
glVertex2i(1095, 330);
glVertex2i(1132, 330);
glVertex2i(1132, 365);
glVertex2i(1095, 365);
glEnd();
glBegin(GL_QUADS); //5st building window1
glColor3ub	(240,230,140);
glVertex2i(1095, 325);
glVertex2i(1132, 325);
glVertex2i(1132, 290);
glVertex2i(1095, 290);
glEnd();


glBegin(GL_QUADS); //s1
glColor3ub	(176,196,222);
glVertex2i(-80, 370);
glVertex2i(90, 370);
glVertex2i(90, 250);
glVertex2i(-80, 250);
glEnd();

glBegin(GL_QUADS); //s2
glColor3ub(176,196,222);
glVertex2i(310, 350);
glVertex2i(370, 350);
glVertex2i(370, 250);
glVertex2i(310, 250);
glEnd();

// trees

glBegin(GL_QUADS); //tree1
glColor3ub(139,69,19);
glVertex2i(400, 350);
glVertex2i(430, 350);
glVertex2i(430, 250);
glVertex2i(400, 250);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(415, 350);
glVertex2i(350, 280);
glVertex2i(480, 280);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(415, 400);
glVertex2i(350, 310);
glVertex2i(480, 310);
glEnd();
glBegin(GL_QUADS); //tree2
glColor3ub(139,69,19);
glVertex2i(-15, 350);
glVertex2i(10, 350);
glVertex2i(10, 250);
glVertex2i(-15, 250);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(0, 350);
glVertex2i(-65, 280);
glVertex2i(65, 280);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(0,100,0);
glVertex2i(0, 400);
glVertex2i(-65, 310);
glVertex2i(65, 310);
glEnd();
glBegin(GL_QUADS); //tree3
glColor3ub(139,69,19);
glVertex2i(183, 350);
glVertex2i(212, 350);
glVertex2i(212, 250);

glColor3ub(128,0,0);

glVertex2i(183, 250);
glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(60,179,113);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
			x=193+50*sin(i);
			y=340+55*cos(i);
			glVertex2f(x,y);
		}
	glEnd();
//treeend


}

if(rainday){

}
else{
//hand12

glBegin(GL_POLYGON);
glColor3ub(255,228,196);
glVertex2i(149, 318);
glVertex2i(100, 306);
glVertex2i(100, 290);
glVertex2i(149, 302);
glVertex2i(200, 295);
glVertex2i(200, 311);
glEnd();

//hand22

glBegin(GL_POLYGON);
glColor3ub(245,222,179);
glVertex2i(121, 318);
glVertex2i(170, 306);
glVertex2i(170, 290);
glVertex2i(121, 302);
glVertex2i(70, 295);
glVertex2i(70, 311);
glEnd();
//glPopMatrix();
//panjabi1
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(55, 325);
glVertex2i(130, 325);
glVertex2i(130, 225);
glVertex2i(55, 225);

//neck1
glColor3ub(245,222,179);
glVertex2i(84, 325);
glVertex2i(84, 346);
glVertex2i(102, 346);
glVertex2i(102, 325);
//design?
glColor3ub(0,0,0);
glVertex2i(91, 325);
glVertex2i(91, 287);
glVertex2i(95, 287);
glVertex2i(95, 325);
glEnd();

glPushMatrix();
glTranslated(0,41,0);
glBegin(GL_QUADS);
//legs11
glColor3ub(245,222,179);
glVertex2i(116, 184);
glVertex2i(106, 184);
glVertex2i(106, 158);
glVertex2i(116, 158);
//legs12
glColor3ub(245,222,179);
glVertex2i(69, 184);
glVertex2i(79, 184);
glVertex2i(79, 158);
glVertex2i(69, 158);
//pants11
glColor3ub(139,69,19);
glVertex2i(118, 184);
glVertex2i(104, 184);
glVertex2i(104, 160);
glVertex2i(118, 160);
//pants12
glColor3ub(139,69,19);
glVertex2i(67, 184);
glVertex2i(81, 184);
glVertex2i(81, 160);
glVertex2i(67, 160);
//shoe11
glColor3ub(0,0,0);
glVertex2i(106, 158);
glVertex2i(130, 158);
glVertex2i(130, 150);
glVertex2i(106, 150);

glVertex2i(130, 158);
glVertex2i(130, 160);
glVertex2i(123, 160);
glVertex2i(123, 158);

//shoe12
glColor3ub(0,0,0);
glVertex2i(69, 158);
glVertex2i(93, 158);
glVertex2i(93, 150);
glVertex2i(69, 150);

glVertex2i(93, 158);
glVertex2i(93, 160);
glVertex2i(86, 160);
glVertex2i(86, 158);

glEnd();
glPopMatrix();
//collar

glBegin(GL_TRIANGLES);
glColor3ub(245,222,179);
glVertex2i(78, 325);
glVertex2i(108, 325);
glVertex2i(93, 310);
glEnd();




//face1
//92,371
glPushMatrix();
    glTranslatef(93, 370, 0);
    glPushMatrix();

    glBegin(GL_POLYGON);
    glColor3ub(245,222,179);

	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=27;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();

    glPushMatrix();
    glTranslatef(93, 360, 0);
    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(245,222,179);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=27;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();
    //tupi
    glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(65, 366);
glVertex2i(56, 380);
glVertex2i(99, 407.5);
glVertex2i(108, 393.5);
glEnd();

glPushMatrix();
glTranslated(-75,0,0);
//faceElements2
//eyebrow
glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(155, 372);
glVertex2i(172, 372);
glVertex2i(172, 370);
glVertex2i(155, 370);
glEnd();
glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(191, 372);
glVertex2i(174, 372);
glVertex2i(174, 370);
glVertex2i(191, 370);
glEnd();
//eyes21
glPushMatrix();
    glTranslatef(163.5, 364, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(0,0,0);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=4;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();

    glPopMatrix();

    //eyes22
glPushMatrix();
    glTranslatef(182.5, 364, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(0,0,0);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=4;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();


    //nose
    glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(172.5, 362);
glVertex2i(175.5, 362);
glVertex2i(175.5, 352);
glVertex2i(172.5, 352);
glEnd();
//smile
glBegin(GL_TRIANGLES);
glColor3ub(0,0,0);
glVertex2i(163.5, 349);
glVertex2i(183.5, 349);
glVertex2i(173.5, 344);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(255,255,255);
glVertex2i(168.5, 348);
glVertex2i(178.5, 348);
glVertex2i(173.5, 346.5);
glEnd();
glPopMatrix();





glPushMatrix();
    glTranslatef(50, 0, 0);
//person2

//panjabi1
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(215, 325);
glVertex2i(140, 325);
glVertex2i(140, 225);
glVertex2i(215, 225);

//neck1
glColor3ub(255,228,196);
glVertex2i(169, 325);
glVertex2i(169, 346);
glVertex2i(187, 346);
glVertex2i(187, 325);
//design?
glColor3ub(0,0,0);
glVertex2i(176, 325);
glVertex2i(176, 287);
glVertex2i(180, 287);
glVertex2i(180, 325);
//legs11
glEnd();

glPushMatrix();
glTranslated(0,41,0);
glBegin(GL_QUADS);
glColor3ub(255,228,196);
glVertex2i(201, 184);
glVertex2i(191, 184);
glVertex2i(191, 158);
glVertex2i(201, 158);
//legs12
glColor3ub(255,228,196);
glVertex2i(154, 184);
glVertex2i(164, 184);
glVertex2i(164, 158);
glVertex2i(154, 158);
//pants11
glColor3ub(25,25,112);
glVertex2i(203, 184);
glVertex2i(189, 184);
glVertex2i(189, 160);
glVertex2i(203, 160);
//pants12
glColor3ub(25,25,112);
glVertex2i(152, 184);
glVertex2i(166, 184);
glVertex2i(166, 160);
glVertex2i(152, 160);
//shoe11
glColor3ub(0,0,0);
glVertex2i(201, 158);
glVertex2i(177, 158);
glVertex2i(177, 150);
glVertex2i(201, 150);

glVertex2i(177, 158);
glVertex2i(177, 160);
glVertex2i(184, 160);
glVertex2i(184, 158);

//shoe12
glColor3ub(0,0,0);
glVertex2i(164, 158);
glVertex2i(140, 158);
glVertex2i(140, 150);
glVertex2i(164, 150);

glVertex2i(140, 158);
glVertex2i(140, 160);
glVertex2i(147, 160);
glVertex2i(147, 158);

glEnd();
glPopMatrix();
//collar

glBegin(GL_TRIANGLES);
glColor3ub(255,228,196);
glVertex2i(163, 325);
glVertex2i(193, 325);
glVertex2i(178, 310);
glEnd();
glPushMatrix();
    glTranslatef(-50, 0, 0);
//hand21
glBegin(GL_POLYGON);
glColor3ub(245,222,179);
glVertex2i(121, 264);
glVertex2i(170, 276);
glVertex2i(170, 260);
glVertex2i(121, 248);
glVertex2i(70, 265);
glVertex2i(70, 281);
glEnd();
glPopMatrix();
//hand11
glBegin(GL_POLYGON);
glColor3ub(255,228,196);
glVertex2i(149, 264);
glVertex2i(100, 276);
glVertex2i(100, 260);
glVertex2i(149, 248);
glVertex2i(200, 265);
glVertex2i(200, 281);
glEnd();



//face1
//92,371
glPushMatrix();
    glTranslatef(178, 370, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(255,228,196);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=27;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();

    glPushMatrix();
    glTranslatef(178, 360, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(255,228,196);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=27;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();
    //tupi
    glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(206, 366);
glVertex2i(215, 380);
glVertex2i(172, 407.5);
glVertex2i(163, 393.5);
glEnd();

//faceElements2
//eyebrow
glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(155, 372);
glVertex2i(172, 372);
glVertex2i(172, 370);
glVertex2i(155, 370);
glEnd();
glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(191, 372);
glVertex2i(174, 372);
glVertex2i(174, 370);
glVertex2i(191, 370);
glEnd();
//eyes21
glPushMatrix();
    glTranslatef(163.5, 364, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(0,0,0);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=4;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();

    glPopMatrix();

    //eyes22
glPushMatrix();
    glTranslatef(182.5, 364, 0);



    glPushMatrix();

    glBegin(GL_POLYGON);
glColor3ub(0,0,0);
	for(int i=0;i<200;i++)
	{
		float pi=3.1416;
		float A=(i*2*pi)/200;
		float r=4;
		float x = r * cos(A);
		float y = r * sin(A);
		glVertex2f(x,y );
	}
	glEnd();
    glPopMatrix();
    glPopMatrix();
    //nose
    glBegin(GL_QUADS);
glColor3ub(0,0,0);
glVertex2i(171.5, 362);
glVertex2i(174.5, 362);
glVertex2i(174.5, 352);
glVertex2i(171.5, 352);
glEnd();
//smile
glBegin(GL_TRIANGLES);
glColor3ub(0,0,0);
glVertex2i(163, 349);
glVertex2i(183, 349);
glVertex2i(173, 344);
glEnd();
glBegin(GL_TRIANGLES);
glColor3ub(255,255,255);
glVertex2i(168, 348);
glVertex2i(178, 348);
glVertex2i(173, 346.5);
glEnd();

glPopMatrix();
}
//helicopter
glPushMatrix();
glTranslatef(_heli,75,0);
glBegin(GL_QUADS);//plane
 	glColor3ub(144,2,29);
    glVertex2f(820, 480);
	glVertex2f(1005, 480);
	glVertex2f(1005, 580);
	glVertex2f(820, 580);
	glEnd();

	glBegin(GL_QUADS);//helipad
 	glColor3ub	(0,0,0);
    glVertex2f(760, 600);
	glVertex2f(1020, 600);
	glVertex2f(1020, 590);
	glVertex2f(760, 590);
	glEnd();
	glBegin(GL_QUADS);//window
 	glColor3ub(255,222,150);
    glVertex2f(920, 520);
	glVertex2f(1000, 520);
	glVertex2f(1000, 570);
	glVertex2f(920, 570);
	glEnd();
	glBegin(GL_QUADS);//helipad C
 	glColor3ub	(112,128,144);
    glVertex2f(890, 590);
	glVertex2f(900, 590);
	glVertex2f(900, 580);
	glVertex2f(890, 580);
	glEnd();
	glBegin(GL_QUADS);//tail1
 	glColor3ub(144,2,29);
    glVertex2f(820, 550);
	glVertex2f(620, 550);
	glVertex2f(620, 530);
	glVertex2f(820, 530);
	glEnd();
	glBegin(GL_QUADS);//tail2
 	glColor3ub(144,2,29);
    glVertex2f(670, 570);
	glVertex2f(650, 570);
	glVertex2f(650, 510);
	glVertex2f(670, 510);
	glEnd();
	glBegin(GL_QUADS);//tail2
 	glColor3ub(139,69,19);
    glVertex2f(620, 545);
	glVertex2f(600, 545);
	glVertex2f(600, 540);
	glVertex2f(620, 540);
	glEnd();
	glBegin(GL_QUADS);//BANNER
 	glColor3ub	(245,245,220);
    glVertex2f(300, 570);
	glVertex2f(600, 570);
	glVertex2f(600, 510);
	glColor3ub(255,192,203);
	glVertex2f(300, 510);
	glEnd();
	glPushMatrix();
    glTranslatef(340, 532, 0);//eidtext
    eidmubarak(0,0,text2);
    glPopMatrix();
	glBegin(GL_QUADS);//DOWN
 	glColor3ub(144,2,29);
    glVertex2f(970, 470);
	glVertex2f(960, 470);
	glVertex2f(960, 480);
	glVertex2f(970, 480);
	glEnd();
	glBegin(GL_QUADS);//DOWN
 	glColor3ub(144,2,29);
    glVertex2f(870, 470);
	glVertex2f(860, 470);
	glVertex2f(860, 480);
	glVertex2f(870, 480);
	glEnd();
	glBegin(GL_QUADS);//DOWN
 	glColor3ub	(0,0,0);
    glVertex2f(990, 470);
	glVertex2f(840, 470);
	glVertex2f(840, 467);
	glVertex2f(990, 467);
	glEnd();
glPopMatrix();


//fatima
glPushMatrix();
glTranslated(-180,95,0);
glPushMatrix();
glScaled(2.45,1.65,0);
//1stpillar
glBegin(GL_QUADS);
glColor3ub(245,245,245);//side
glVertex2i(250,280);
glVertex2i(255,280);
glVertex2i(255,20);
glVertex2i(250,20);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//middle
glVertex2i(255,280);
glVertex2i(267,280);
glVertex2i(267,20);
glVertex2i(255,20);
glEnd();

glBegin(GL_QUADS);
glColor3ub(245,245,245);//side
glVertex2i(267,280);
glVertex2i(272,280);
glVertex2i(272,20);
glVertex2i(267,20);
glEnd();
//2ndinnerminarof1stpillar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+5*sin(i);
           y=244+8*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(261,256);
glVertex2i(257,249);
glVertex2i(265,249);
glEnd();

glBegin(GL_QUADS);
glColor3ub(128,128,128);//middlebox
glVertex2f(258,240);
glVertex2f(264,240);
glVertex2f(264,200);
glVertex2f(258,200);
glEnd();


glBegin(GL_QUADS);
glColor3ub(255,255,255);//2ndline
glVertex2i(248,200);
glVertex2i(274,200);
glVertex2i(274,195);
glVertex2i(248,195);
glEnd();

//1stminarminiminars
glBegin(GL_TRIANGLE_FAN);//1stinstick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+2.5*sin(i);
           y=334+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//2ndinstick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+1.5*sin(i);
           y=343+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+2.5*sin(i);
           y=355+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//1ststick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(261,352);
glVertex2i(260,333);
glVertex2i(262,333);
glEnd();

//1stpillarminar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+14*sin(i);
           y=304+20*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(261,332);
glVertex2i(250,316);
glVertex2i(272,316);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//base
glVertex2f(250,288);
glVertex2f(272,288);
glVertex2f(272,282);
glVertex2f(250,282);
glEnd();


glBegin(GL_QUADS);
glColor3ub(255,255,255);//toplineof1stpillar
glVertex2i(248,282);
glVertex2i(274,282);
glVertex2i(274,277);
glVertex2i(248,277);
glEnd();


//1stbaseL
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(272,120);
glVertex2i(339,120);
glVertex2i(339,20);
glVertex2i(272,20);
glEnd();

//innerminar1
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=293+9*sin(i);
           y=82+11*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(293,99);
glVertex2i(287,90);
glVertex2i(299,90);
glEnd();

glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(287,75);
glVertex2i(299,75);
glVertex2i(299,35);
glVertex2i(287,35);
glEnd();

//innerminar2
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=321+9*sin(i);
           y=82+11*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLES);
glColor3ub(128,128,128);
glVertex2i(321,98);
glVertex2i(315,89);
glVertex2i(327,89);
glEnd();


glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(315,75);
glVertex2i(327,75);
glVertex2i(327,35);
glVertex2i(315,35);
glEnd();

//1stbaseaboveline
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(272,130);
glVertex2i(339,130);
glVertex2i(339,125);
glVertex2i(272,125);
glEnd();
//1stinnermiarof1stpillar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=261+5*sin(i);
           y=170+8*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(261,183);
glVertex2i(257,176);
glVertex2i(265,176);

glEnd();
glBegin(GL_QUADS);
glColor3ub(128,128,128);//middlebox
glVertex2f(258,170);
glVertex2f(264,170);
glVertex2f(264,130);
glVertex2f(258,130);
glEnd();




glBegin(GL_QUADS);
glColor3ub(255,255,255);//3rdlineofpillar
glVertex2i(248,130);
glVertex2i(274,130);
glVertex2i(274,126);
glVertex2i(248,126);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);//4thlineofpillar
glVertex2i(248,120);
glVertex2i(274,120);
glVertex2i(274,116);
glVertex2i(248,116);
glEnd();


glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(272,132);
glVertex2i(339,132);
glVertex2i(339,130);
glVertex2i(272,130);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(272,125);
glVertex2i(339,125);
glVertex2i(339,122);
glVertex2i(272,122);
glEnd();


glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(272,122);
glVertex2i(339,122);
glVertex2i(339,118);
glVertex2i(272,118);
glEnd();
//grey
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(272,122);
glVertex2i(339,122);
glVertex2i(339,113);
glVertex2i(272,113);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(272,113);
glVertex2i(339,113);
glVertex2i(339,110);
glVertex2i(272,110);
glEnd();

//smallquardforwhite
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(272,127);
glVertex2i(274,127);
glVertex2i(274,125);
glVertex2i(272,125);
glEnd();

//2ndpillaron1stbase
glBegin(GL_QUADS);
glColor3ub(255,255,255);//side
glVertex2i(300,195);
glVertex2i(308,195);
glVertex2i(308,132);
glVertex2i(300,132);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//middle
glVertex2i(308,195);
glVertex2i(328,195);
glVertex2i(328,132);
glVertex2i(308,132);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);//side
glVertex2i(328,195);
glVertex2i(336,195);
glVertex2i(336,132);
glVertex2i(328,132);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);//topof2minar
glVertex2i(298,200);
glVertex2i(338,200);
glVertex2i(338,195);
glVertex2i(298,195);
glEnd();

//baseinnerminar
glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(313,166);
glVertex2i(323,166);
glVertex2i(323,132);
glVertex2i(313,132);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(318,186);
glVertex2i(313,178);
glVertex2i(323,178);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+7.5*sin(i);
           y=172+8.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//2minar
glBegin(GL_QUADS);
glColor3ub(211,211,211);//base2minar
glVertex2i(303,210);
glVertex2i(333,210);
glVertex2i(333,200);
glVertex2i(303,200);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(318,264);
glVertex2i(303,244);
glVertex2i(333,244);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+20*sin(i);
           y=228+28*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
//2ndstick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(318,295);
glVertex2i(317,259);
glVertex2i(319,259);
glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+3*sin(i);
           y=289+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+1*sin(i);
           y=278+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+1.5*sin(i);
           y=273+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//4thpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=318+3*sin(i);
           y=267+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


//whitelinebefore2ndbase
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(339,140);
glVertex2i(340,140);
glVertex2i(340,20);
glVertex2i(339,20);
glEnd();
//2ndbaseL
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(340,140);
glVertex2i(385,140);
glVertex2i(385,20);
glVertex2i(340,20);
glEnd();
//2ndbaseinnerminar
glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(355,70);
glVertex2i(371,70);
glVertex2i(371,20);
glVertex2i(355,20);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(363,100);
glVertex2i(354,90);
glVertex2i(372,90);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=363+13*sin(i);
           y=80+14*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


//2ndbaseabovelines
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(340,140);
glVertex2i(385,140);
glVertex2i(385,138);
glVertex2i(340,138);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(338,134);
glVertex2i(385,134);
glVertex2i(385,131);
glVertex2i(338,131);
glEnd();
//grey
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(340,131);
glVertex2i(385,131);
glVertex2i(385,123);
glVertex2i(340,123);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(338,123);
glVertex2i(385,123);
glVertex2i(385,121);
glVertex2i(338,121);
glEnd();

//3rdpillaron2ndbase
glBegin(GL_QUADS);//side
glColor3ub(211,211,211);
glVertex2i(367,164);
glVertex2i(382,164);
glVertex2i(382,140);
glVertex2i(367,140);
glEnd();

glBegin(GL_QUADS);//side
glColor3ub(255,255,255);
glVertex2i(367,164);
glVertex2i(352,164);
glVertex2i(352,140);
glVertex2i(367,140);
glEnd();

glBegin(GL_QUADS);//quardabove3rdminar
glColor3ub(255,255,255);
glVertex2i(350,168);
glVertex2i(384,168);
glVertex2i(384,164);
glVertex2i(350,164);
glEnd();
//3rdminar
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(354,180);
glVertex2i(380,180);
glVertex2i(380,168);
glVertex2i(354,168);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(367,235);
glVertex2i(354,220);
glVertex2i(380,220);
glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=367+20*sin(i);
           y=199+27*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//3rdstick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(367,268);
glVertex2i(366,234);
glVertex2i(368,234);
glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=367+3*sin(i);
           y=260+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=367+1*sin(i);
           y=250+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=367+1.5*sin(i);
           y=243+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//4thpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=367+2.5*sin(i);
           y=237+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


//3rdbase
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(385,170);
glVertex2i(440,170);
glVertex2i(440,20);
glVertex2i(385,20);
glEnd();
//innerminar
glBegin(GL_QUADS);
glColor3ub(105,105,105);
glVertex2i(401,100);
glVertex2i(425,100);
glVertex2i(425,20);
glVertex2i(401,20);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(105,105,105);
glVertex2i(413,142);
glVertex2i(401,122);
glVertex2i(425,122);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(105,105,105);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=413+16*sin(i);
           y=110+17*cos(i);
			glVertex2f(x,y);
		}
		glEnd();



//3rdbaseavobelines
//grey
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(385,171);
glVertex2i(440,171);
glVertex2i(440,163);
glVertex2i(385,163);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(383,163);
glVertex2i(442,163);
glVertex2i(442,159);
glVertex2i(383,159);
glEnd();



//5thminar
glBegin(GL_QUADS);//side
glColor3ub(255,255,255);
glVertex2i(443,164);
glVertex2i(458,164);
glVertex2i(458,140);
glVertex2i(443,140);
glEnd();

glBegin(GL_QUADS);//side
glColor3ub(211,211,211);
glVertex2i(458,164);
glVertex2i(473,164);
glVertex2i(473,140);
glVertex2i(458,140);
glEnd();

glBegin(GL_QUADS);//topof4thpillar
glColor3ub(255,255,255);
glVertex2i(440,168);
glVertex2i(475,168);
glVertex2i(475,164);
glVertex2i(440,164);
glEnd();
//5thminar
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(443,178);
glVertex2i(473,178);
glVertex2i(473,168);
glVertex2i(443,168);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(458,237);
glVertex2i(443,218);
glVertex2i(473,218);
glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=458+20*sin(i);
           y=199+27*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//5thstick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(458,270);
glVertex2i(457,236);
glVertex2i(459,236);
glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=458+3*sin(i);
           y=260+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=458+1*sin(i);
           y=250+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=458+1.5*sin(i);
           y=245+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//4thpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=458+2.5*sin(i);
           y=239+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//4thminar
glBegin(GL_QUADS);//baseof4thminar
glColor3ub(211,211,211);
glVertex2i(388,183);
glVertex2i(436,183);
glVertex2i(436,174);
glVertex2i(388,174);
glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(255,255,255);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+38*sin(i);
           y=221+50*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+37*sin(i);
           y=221+51*cos(i);
			glVertex2f(x,y);
		}
		glEnd();



glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(412,284);
glVertex2i(388,260);
glVertex2i(436,260);
glEnd();

glBegin(GL_QUADS);//topquardof3rdpillar
glColor3ub(255,255,255);
glVertex2i(383,174);
glVertex2i(442,174);
glVertex2i(442,171);
glVertex2i(383,171);
glEnd();

//4thstick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(412,332);
glVertex2i(411,283);
glVertex2i(413,283);
glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+4*sin(i);
           y=325+5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+1.5*sin(i);
           y=313+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+2.5*sin(i);
           y=297+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//4thpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=412+4*sin(i);
           y=286+5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//4thbase
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(440,140);
glVertex2i(485,140);
glVertex2i(485,20);
glVertex2i(440,20);
glEnd();

//4thbaseinnerminar
glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(455,70);
glVertex2i(471,70);
glVertex2i(471,20);
glVertex2i(455,20);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(463,100);
glVertex2i(454,90);
glVertex2i(472,90);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=463+13*sin(i);
           y=80+14*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
//4thbasewhiteline
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(485,140);
glVertex2i(486,140);
glVertex2i(486,20);
glVertex2i(485,20);
glEnd();

//4thbaseabovelines
//1stwhite
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(440,140);
glVertex2i(486,140);
glVertex2i(486,138);
glVertex2i(440,138);
glEnd();

//2ndwhite
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(440,134);
glVertex2i(488,134);
glVertex2i(488,131);
glVertex2i(440,131);
glEnd();

//grey
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(440,131);
glVertex2i(485,131);
glVertex2i(485,123);
glVertex2i(440,123);
glEnd();

//white
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(440,123);
glVertex2i(488,123);
glVertex2i(488,121);
glVertex2i(440,121);
glEnd();

//5thbase
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(486,130);
glVertex2i(560,130);
glVertex2i(560,20);
glVertex2i(486,20);
glEnd();

//innerminar1
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+9*sin(i);
           y=82+11*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(507,98);
glVertex2i(501,89);
glVertex2i(513,89);
glEnd();

glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(501,75);
glVertex2i(513,75);
glVertex2i(513,35);
glVertex2i(501,35);
glEnd();

//innerminar2
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=536+9*sin(i);
           y=82+11*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLES);
glColor3ub(128,128,128);
glVertex2i(536,99);
glVertex2i(529,90);
glVertex2i(543,90);
glEnd();


glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(530,75);
glVertex2i(542,75);
glVertex2i(542,35);
glVertex2i(530,35);
glEnd();
//lineabove5thbase
glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(486,130);
glVertex2i(560,130);
glVertex2i(560,128);
glVertex2i(486,128);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(486,123);
glVertex2i(560,123);
glVertex2i(560,121);
glVertex2i(486,121);
glEnd();


//grey
glBegin(GL_QUADS);
glColor3ub(169,169,169);
glVertex2i(486,121);
glVertex2i(560,121);
glVertex2i(560,113);
glVertex2i(486,113);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);
glVertex2i(486,113);
glVertex2i(560,113);
glVertex2i(560,110);
glVertex2i(486,110);
glEnd();
//5thpillar
glBegin(GL_QUADS);
glColor3ub(255,255,255);//side
glVertex2i(489,195);
glVertex2i(497,195);
glVertex2i(497,130);
glVertex2i(489,130);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//middle
glVertex2i(497,195);
glVertex2i(517,195);
glVertex2i(517,130);
glVertex2i(497,130);
glEnd();
//baseinnerminar
glBegin(GL_QUADS);
glColor3ub(128,128,128);
glVertex2i(502,166);
glVertex2i(512,166);
glVertex2i(512,132);
glVertex2i(502,132);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(507,186);
glVertex2i(502,178);
glVertex2i(512,178);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+7.5*sin(i);
           y=172+8.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_QUADS);
glColor3ub(255,255,255);//side
glVertex2i(517,195);
glVertex2i(525,195);
glVertex2i(525,130);
glVertex2i(517,130);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);//topof6thpillar
glVertex2i(487,200);
glVertex2i(527,200);
glVertex2i(527,195);
glVertex2i(487,195);
glEnd();
//6thminar
glBegin(GL_QUADS);
glColor3ub(211,211,211);
glVertex2i(490,210);
glVertex2i(524,210);
glVertex2i(524,200);
glVertex2i(490,200);
glEnd();

 glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(507,265);
glVertex2i(490,244);
glVertex2i(524,244);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+20*sin(i);
           y=229+27*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//7thstick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(507,300);
glVertex2i(506,264);
glVertex2i(508,264);
glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+3*sin(i);
           y=290+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+1*sin(i);
           y=280+2*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//3rdpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+1.5*sin(i);
           y=275+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//4thpoint
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=507+3*sin(i);
           y=267+4*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//lastpillar
glBegin(GL_QUADS);
glColor3ub(255,255,255);//side
glVertex2i(560,280);
glVertex2i(565,280);
glVertex2i(565,20);
glVertex2i(560,20);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//middle
glVertex2i(565,280);
glVertex2i(577,280);
glVertex2i(577,20);
glVertex2i(565,20);
glEnd();

glBegin(GL_QUADS);
glColor3ub(245,245,245);//side
glVertex2i(577,280);
glVertex2i(582,280);
glVertex2i(582,20);
glVertex2i(577,20);
glEnd();




glBegin(GL_QUADS);
glColor3ub(255,255,255);//toplineofpillar
glVertex2i(558,285);
glVertex2i(584,285);
glVertex2i(584,280);
glVertex2i(558,280);
glEnd();

//1stinnerminarof1stpillar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+4.5*sin(i);
           y=244+8*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(571,256);
glVertex2i(568,249);
glVertex2i(574,249);
glEnd();

glBegin(GL_QUADS);
glColor3ub(128,128,128);//middlebox
glVertex2f(568,240);
glVertex2f(574,240);
glVertex2f(574,200);
glVertex2f(568,200);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255,255,255);//2ndline
glVertex2i(558,195);
glVertex2i(584,195);
glVertex2i(584,200);
glVertex2i(558,200);
glEnd();

//1stminarminiminars
glBegin(GL_TRIANGLE_FAN);//1stinstick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+2.5*sin(i);
           y=334+3.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//2ndinstick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+1.5*sin(i);
           y=342+2.5*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);//abovestick
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+2*sin(i);
           y=355+3*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

//laststick
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(571,358);
glVertex2i(570,331);
glVertex2i(572,331);
glEnd();

//lastpillarminar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(211,211,211);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+14*sin(i);
           y=304+18*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_POLYGON);
glColor3ub(211,211,211);
glVertex2i(571,332);
glVertex2i(560,316);
glVertex2i(582,316);
glEnd();

glBegin(GL_QUADS);
glColor3ub(211,211,211);//baseoflastminar
glVertex2i(560,293);
glVertex2i(582,293);
glVertex2i(582,285);
glVertex2i(560,285);
glEnd();

//2ndinnerminarof1stpillar
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(128,128,128);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=571+5*sin(i);
           y=173+8*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glBegin(GL_POLYGON);
glColor3ub(128,128,128);
glVertex2i(571,186);
glVertex2i(568,179);
glVertex2i(574,179);
glEnd();

glBegin(GL_QUADS);
glColor3ub(128,128,128);//middlebox
glVertex2f(568,170);
glVertex2f(574,170);
glVertex2f(574,130);
glVertex2f(568,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255,255,255);//3rdlineofpillar
glVertex2i(558,130);
glVertex2i(584,130);
glVertex2i(584,126);
glVertex2i(558,126);
glEnd();

glBegin(GL_QUADS);
glColor3ub(255,255,255);//4thlineofpillar
glVertex2i(558,120);
glVertex2i(584,120);
glVertex2i(584,116);
glVertex2i(558,116);
glEnd();
glPopMatrix();
glPopMatrix();
glBegin(GL_QUADS);
//roads
glColor3ub(128,128,128);
glVertex2i(-100,0);
glVertex2i(1280,0);
glVertex2i(1280,130);
glVertex2i(-100,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(0, 0, 0);
glVertex2i(-100,125);
glVertex2i(1280,125);
glVertex2i(1280,130);
glVertex2i(-100,130);
glEnd();
//foootpath
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(-100,125);
glVertex2i(0,125);
glVertex2i(0,130);
glVertex2i(-100,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(100,125);
glVertex2i(200,125);
glVertex2i(200,130);
glVertex2i(100,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(300,125);
glVertex2i(400,125);
glVertex2i(400,130);
glVertex2i(300,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(500,125);
glVertex2i(600,125);
glVertex2i(600,130);
glVertex2i(500,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(700,125);
glVertex2i(800,125);
glVertex2i(800,130);
glVertex2i(700,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(1000,125);
glVertex2i(900,125);
glVertex2i(900,130);
glVertex2i(1000,130);
glEnd();
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(1100,125);
glVertex2i(1200,125);
glVertex2i(1200,130);
glVertex2i(1100,130);
glEnd();
//linediv
glBegin(GL_QUADS);
glColor3ub(255, 255, 255);
glVertex2i(-100,57);
glVertex2i(1280,57);
glVertex2i(1280,60);
glVertex2i(-100,60);
glEnd();
//stop
glBegin(GL_QUADS);
glColor3ub(0, 0, 0);
glVertex2i(350,210);
glVertex2i(353,210);
glVertex2i(353,130);
glVertex2i(350,130);
glEnd();
glBegin(GL_POLYGON);
glColor3ub(255, 0, 0);
glVertex2i(336,210);
glVertex2i(366,210);
glVertex2i(373,230);
glVertex2i(366,250);
glVertex2i(336,250);
glVertex2i(329,230);
glEnd();
glPushMatrix();
    glTranslatef(333, 227, 0);
    slow(0,0,text);
    glPopMatrix();


//car
//firstcar

glPushMatrix();
glScalef(.75,.85,0);
glPushMatrix();
glTranslatef(_carmove1,-315,0);
glBegin(GL_QUADS);
glColor3ub(128,0,0);
glVertex2i(60,490);
glVertex2i(385,490);
glVertex2i(385,440);
glVertex2i(60,440);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(128,0,0);
glVertex2i(150,535);
glVertex2i(280,535);
glVertex2i(350,490);
glVertex2i(100,490);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(25,25,112);
glVertex2i(153,530);
glVertex2i(214,530);
glVertex2i(214,496);
glVertex2i(114,496);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(25,25,112);
glVertex2i(218,530);
glVertex2i(277,530);
glVertex2i(332,496);
glVertex2i(218,496);
glEnd();


glBegin(GL_TRIANGLE_FAN);
		glColor3ub(0,0,0);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=153+30*sin(i);
           y=449+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(169,169,169);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=153+22*sin(i);
           y=448+17*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


		glEnd();




glBegin(GL_TRIANGLE_FAN);
		glColor3ub(0,0,0);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=290+30*sin(i);
           y=449+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(169,169,169);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=290+22*sin(i);
           y=448+17*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
		glPopMatrix();


//2ndcar
glPushMatrix();
glTranslatef(_carmove2,-215,0);
glBegin(GL_QUADS);
glColor3ub(0,0,255);
glVertex2i(60,290);
glVertex2i(385,290);
glVertex2i(385,240);
glVertex2i(60,240);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(0,0,255);
glVertex2i(155,335);
glVertex2i(310,335);
glVertex2i(350,290);
glVertex2i(90,290);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(25,25,112);
glVertex2i(158,330);
glVertex2i(221,330);
glVertex2i(221,292);
glVertex2i(100,292);
glEnd();

glBegin(GL_POLYGON);
glColor3ub(25,25,112);
glVertex2i(226,330);
glVertex2i(310,330);
glVertex2i(339,292);
glVertex2i(226,292);
glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(0,0,0);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=160+30*sin(i);
           y=248+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(169,169,169);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=160+22*sin(i);
           y=248+17*cos(i);
			glVertex2f(x,y);
		}
		glEnd();


		glEnd();

glBegin(GL_TRIANGLE_FAN);
		glColor3ub(0,0,0);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=290+30*sin(i);
           y=248+25*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glBegin(GL_TRIANGLE_FAN);
		glColor3ub(169,169,169);
		for(i=0;i<=2*3.14;i+=0.0001)
		{
           x=290+22*sin(i);
           y=248+17*cos(i);
			glVertex2f(x,y);
		}
		glEnd();
glPopMatrix();





		glPopMatrix();




glFlush();
}

void update(int value) {

	_cloudmove1 += 10.0;
	if (_cloudmove1 > 1300)
    {
        _cloudmove1 -= 1700;
    }
    _cloudmove2 += 17.0;
    if (_cloudmove2 > 700)
    {
        _cloudmove2 -= 1700;
    }
    _cloudmove3 += 31.0;
    if (_cloudmove3 > 300)
    {
        _cloudmove3 -= 1700;
    }
    _cloudmove4 += 31.0;
    if (_cloudmove4 > 1400)
    {
        _cloudmove4 -= 1700;
    }
    _cloudmove5 += 31.0;
    if (_cloudmove5 > 1100)
    {
        _cloudmove5 -= 1700;
    }
    _cloudmove6 += 17.0;
    if (_cloudmove6 > 864)
    {
        _cloudmove6 -= 1700;
    }
    _cloudmove7 += 31.0;
    if (_cloudmove7 > 300)
    {
        _cloudmove7 -= 1700;
    }
    _cloudmove8 += 31.0;
    if (_cloudmove8 > 500)
    {
        _cloudmove8 -= 1700;
    }
    _cloudmove9 += 31.0;
    if (_cloudmove9 > 1300)
    {
        _cloudmove9 -= 1700;
    }
    _heli += 60.0;
    if (_heli > 1000)
    {
        _heli -= 2500;
    }
    if(move1){
    _carmove1 += 50.0;
    if (_carmove1 > 1700)
    {
        _carmove1 -= 2100;
    }}
    if(move2){
    _carmove2 -= 50.0;
    if (_carmove2 < -500)
    {
        _carmove2 += 2200;
    }}
    n+=4;
    if (n > 23)
    {
        n =0;
    }
    glutPostRedisplay();
	glutTimerFunc(5, update, 0);

}
void Rain(int value){

if(rainday){

    _rain += 0.01f;

    glBegin(GL_POINTS);
    for(int i=1;i<=1000;i++)
    {

        int x=rand() % 1380,y=rand() % 720;

        glBegin(GL_LINES);
        glColor3f(1.0, 1.0, 1.0);

        glVertex2d(x-100,y);
        glVertex2d(x-107,y+5);


        glEnd();
    }

	glutPostRedisplay();
	glutTimerFunc(1, Rain, 0);

    glFlush();


}
}

void Night(int value){

if(night){



    nview=1;
	glutPostRedisplay();
    glutTimerFunc(5, Night, 0);


}
}

void myKeyboard(unsigned char key, int x, int y){
	switch (key)
	{


    case 'r':
        rainday = true;
Rain(_rain);
        sndPlaySound("rain.wav",SND_ASYNC|SND_LOOP);
        sndPlaySound("rain.wav",SND_MEMORY|SND_ASYNC);
        break;

    case 'e':
        rainday = false;
        sndPlaySound("eid.wav",SND_ASYNC|SND_LOOP);
		sndPlaySound("eid.wav",SND_MEMORY|SND_ASYNC);
        break;

    case 'n':

        night = true;
        Night(_nt);
        break;

    case 'm':
        night = false;
        nview = 0;
        break;

    case 'd':
        move1 = true;

        break;

    case 's':
        move1 = false;

        break;

    case 'x':
        move2 = true;

        break;

    case 'z':
        move2 = false;

        break;

    case 27:
        exit(0);
        break;

	default:
	break;
	}
}



void myInit (void)
{

glClearColor(0.0, 0.0, 0.0, 0.0);
glMatrixMode(GL_PROJECTION);
glLoadIdentity();
gluOrtho2D(-100, 1280.0, 0.0, 720.0);
}

int main(int argc, char** argv)
{
    cout << endl << "     Eid Festival                     " << endl << endl;

    cout << "Press D to move the Red car" << endl << endl;
    cout << "Press S to Stop the Red car" << endl << endl;

    cout << "Press X to move the Blue car" << endl << endl;
    cout << "Press Z to Stop the Blue car" << endl << endl;

    cout << "Press R for Rain " << endl << endl;
    cout << "Press E for Stop Rain" << endl << endl;

    cout << "Press N for Night " << endl << endl;
    cout << "Press M for Day" << endl << endl;

    cout << "Press ESC to exit" << endl << endl;
glutInit(&argc, argv);
glutInitDisplayMode (GLUT_SINGLE | GLUT_RGB);
glutInitWindowSize (1280, 720);
glutInitWindowPosition (100, 150);
glutCreateWindow("Eid Festival");
glutDisplayFunc(myDisplay);
glutKeyboardFunc(myKeyboard);
sndPlaySound("eid.wav",SND_ASYNC|SND_LOOP);
sndPlaySound("eid.wav",SND_MEMORY|SND_ASYNC);
glutTimerFunc(100, update, 0);
myInit();
glutMainLoop();
return 0;
}
