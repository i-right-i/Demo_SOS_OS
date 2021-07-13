### Just like a simple raylib app.

```c
/* Includes not shown */
#define ZERO 0
#define REC_SIZE 50
#define REC_PADDING REC_SIZE - 1
#define STEP_SIZE 2

void x_y_move_bounds();

int x,y,toggle_x,toggle_y,screen_size_x,screen_size_y;

 int main()
 {
	sos_io_init();
 	
	Color color;
	color.r = 20;
	color.g = 20;
	color.b = 20;
	color.a = 255;	

	screen_size_x = GetScreenWidth();
	screen_size_y = GetScreenHeight();
	x = screen_size_x / 2;
	y = screen_size_y / 2;
	toggle_x = STEP_SIZE;
	toggle_y = STEP_SIZE;

	while(1)
	{
	BeginDrawing();
	ClearBackground(color);
	DrawRectangle(x, y, REC_SIZE, REC_SIZE, (Color){30,30,180,255});
	EndDrawing();
	x_y_move_bounds();
	}
    return 0;
 }


void x_y_move_bounds()
{
	if(  (x>(screen_size_x - REC_PADDING))  || (x < ZERO) ) toggle_x = toggle_x * (-1);
	if(  (y>(screen_size_y - REC_PADDING))  || (y < ZERO) ) toggle_y = toggle_y * (-1);

	x += toggle_x;
	y += toggle_y;	
	
}
```


