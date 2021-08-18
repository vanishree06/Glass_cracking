#include<GL/glut.h>
#include<stdio.h>
#include<math.h>
#include<stdlib.h>
#include<stdarg.h>

GLfloat vertices[24]={	-1.0, -0.20, -1.0,  1.0, -0.20, -1.0,  1.0,  0.20,
			-1.0, -1.0,  0.20, -1.0, -1.0, -0.20,  1.0,  1.0,
			-0.20,  1.0,  1.0, 0.20,  1.0, -1.0,  0.20,  1.0};
GLfloat colors[24]= {	 0.0, 0.0, 0.0, 1.0, 0.0, 0.0, 1.0, 1.0, 
			 0.0, 0.0, 1.0, 0.0, 0.0, 0.0, 1.0, 1.0,
			 0.0, 1.0, 1.0, 1.0, 1.0, 0.0, 1.0, 1.0};
GLubyte cubeIndices[24]={0, 3, 2, 1, 2, 3, 7, 6, 0, 4, 7, 3, 1, 2, 6, 5, 4, 5, 6, 7, 0, 1, 5, 4};
static GLfloat theta[3]={30.0, 40.0, 0.0};

GLint v=60,id;
GLint flag=0,flag1=0,flag2=0;
GLfloat y=5.0,sy=0.04;
GLfloat R=1.0,G=0.0,B=0.0;
GLint submenu1;
void lines();
void sphere();

void drawstring(float x,float y,float z,char *string)
{
	char *c;
	glRasterPos3f(x,y,z);
	for(c=string;*c!='\0';c++)
	{
		glutBitmapCharacter(GLUT_BITMAP_TIMES_ROMAN_24,*c);
	}
}

void screen()
{      
	glColor3f(0.5,0.0,1.0);
	drawstring(-1.5,2.6,0.0,"CGV MINI PROJECT");
        glColor3f(1.0,0.0,0.0);
        drawstring(-1.3,2.2,0.0,"GLASS CRACKING");
        glColor3f(0.5,1.0,0.0);
	drawstring(-1.0,1.8,0.0,"SUNSHINERS");
	glColor3f(0.5,0.0,1.0);
	drawstring(-1.2,1.4,0.0,"Submitted By:");
        glColor3f(1.0,0.0,0.5);
	drawstring(-1.2,1.0,0.0," Your Name  ");
        drawstring(-1.2,0.6,0.0,"  Your Name");
  	glColor3f(0.0,0.5,1.5);
        drawstring(-1.2,-0.0,0.0,"USN:");
	drawstring(-1.2,-0.4,0.0,"USN:");
	glColor3f(0.5,0.0,1.0);
	drawstring(-0.6,-1.0,0.0,"GUIDE");
 	glColor3f(1.0,0.5,0.0);
	drawstring(-1.2,-1.4,0.0,"Prof ");
	glColor3f(0.0,0.0,0.0);
	drawstring(-1.8,-2.6,0.0,"Press 'a' for instructions");
        glFlush();        
        glutSwapBuffers();
}

void instructions()
{
	glColor3f(1.0,1.0,0.0);	
	drawstring(-2.6,2.2,0.0,"press 'i/I' for increment the ball speed");
        drawstring(-2.6,1.8,0.0,"press 'd/D' for decrement the ball speed");
        drawstring(-2.6,1.4,0.0,"press 'right btn of the mouse' for menu");
	glColor3f(0.0,0.0,0.0);
        drawstring(-1.7,0.8,0.0,"press 's' to start the project");
}
void mytimer(int v)
{
	glutIdleFunc(sphere);
	glutPostRedisplay();
	glutTimerFunc(100, mytimer, v);
}

void sphere()
{
        glColor3f(R,G,B);
        glTranslatef(0.0,y,0.0);
        glutSolidSphere(0.3,60,60);

}  

void mykeyboard(unsigned char key,int x,int y)
{
      
       if(key=='a'||key=='a')
	{  
	   flag1=1;  
	   flag=1;
	}
        
	if(key=='s'||key=='S')
	{  
	   flag2=2;  
	   flag1=2;
	}
	if(key=='i'||key=='I')
        {
           sy=sy+0.01;
 	   lines();
        }
        if(key=='d'||key=='D')
        {
	   sy=sy-0.001;
           lines();
        }
} 

void lines()
{
        
        glLineWidth(3.0);
        glBegin(GL_LINES);
               glVertex3f(0.1,0.3,0.1);
               glVertex3f(0.2,0.4,0.1);
	       glVertex3f(0.1,0.05,0.3);
               glVertex3f(0.4,0.06,0.4);
               glVertex3f(0.001,0.0002,0.4);
               glVertex3f(0.4,0.0001,0.8); 
               glVertex3f(-0.2,-0.1,0.8);
               glVertex3f(-0.6,0.4,0.95);
               glVertex3f(-0.3,-0.8,0.4);
               glVertex3f(-0.7,0.3,0.8);
               glVertex3f(-0.5,0.1,0.4);
               glVertex3f(-0.7,-0.7,0.06);
               glVertex3f(-0.6,0.3,0.4);
               glVertex3f(-0.8,-0.2,0.06);
	       glVertex3f(-0.85,0.5,0.6);
               glVertex3f(-0.9,0.4,0.10);
         glEnd();
}   

void menu(int id)
{
    switch(id)
    {
       case 1:exit(0);
              break;
    }
}

void color(int id)
{
     switch(id)
     {
       case 2:R=1.0,G=0.0,B=0.0;
	      glutPostRedisplay();
              break;
       case 3:R=0.0,G=1.0,B=0.0;
	      glutPostRedisplay();
              break;
       case 4:R=0.0,G=0.0,B=1.0;
	      glutPostRedisplay();
              break;     
     }
} 

	 
void display()
{
       glClearColor(0.2,0.3,0.0,0.0);
       glClear(GL_COLOR_BUFFER_BIT|GL_DEPTH_BUFFER_BIT);
       if(flag==0)
       {
	glutIdleFunc(screen);
        screen();
	glutSwapBuffers();
       }
       if(flag1==1)
       {  
          glutIdleFunc(instructions);
          instructions();
          glutSwapBuffers();
        }
        if(flag2==2)
        {
        glLoadIdentity();
        glTranslatef(0.0,-2.0,0.0);
 	glRotatef(theta[0],1.0,0.0,0.0);
 	glRotatef(theta[1],0.0,1.0,0.0);
 	glRotatef(theta[2],0.0,0.0,1.0);
 	glDrawElements(GL_QUADS, 24, GL_UNSIGNED_BYTE, cubeIndices);
 	sphere();
        if(y>0.5)
        {
          y=y-sy;
        }
       else if(y=0.5)
        { 
	  lines();
	}
        }        
        glFlush();
        glutSwapBuffers();
}

void myReshape(int w, int h)
{
	glViewport(0,0, w, h);
	glMatrixMode(GL_PROJECTION);
	glLoadIdentity();
	if(w<=h)
		glOrtho(-3.0,3.0,-3.0*(GLfloat)h/(GLfloat)w, 3.0*(GLfloat)h/(GLfloat)w,-3.0,3.0);
	else
		glOrtho(-3.0*(GLfloat)w/(GLfloat)h, 3.0*(GLfloat)w/(GLfloat)h, -3.0,3.0,-3.0,3.0);
	glMatrixMode(GL_MODELVIEW);
	glutPostRedisplay();
}
int main(int argc, char **argv)
{
	glutInit(&argc, argv);
	glutInitDisplayMode(GLUT_RGB | GLUT_DEPTH);
	glutInitWindowSize(500,500);
	glutCreateWindow("my window");
        glutReshapeFunc(myReshape);
	glutDisplayFunc(display);
	submenu1=glutCreateMenu(color);
                  glutAddMenuEntry("red",2);
                  glutAddMenuEntry("green",3);
                  glutAddMenuEntry("blue",4);
        glutCreateMenu(menu);
        glutAddMenuEntry("quit",1);
	glutAddSubMenu("color",submenu1);
        glutAttachMenu(GLUT_RIGHT_BUTTON);
	glutKeyboardFunc(mykeyboard);
	glEnable(GL_DEPTH_TEST);
	glutTimerFunc(25, mytimer, v);
	glEnableClientState(GL_COLOR_ARRAY);
	glEnableClientState(GL_VERTEX_ARRAY);
	glVertexPointer(3,GL_FLOAT, 0, vertices);
	glColorPointer(3, GL_FLOAT, 0, colors);
	glutMainLoop();
}
