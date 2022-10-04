/*
School life
*/

//Class Objects
player p;
Map m;
controls c;
Scene scene;
Battle b;

// All buttons in current version of the game
Buttons sleepButton;
Buttons eatButton;
Buttons studyButton;
Buttons socialButton;
Buttons backButton;
Buttons contButton;

//images and assets
PImage startscreen;
PImage playerImages[];
PImage mapTiles[];

PImage battle;
PImage enemy1;

//Originally supposed to be tilesets, they were turned into images due to inconveniences 
PImage socialmap;
PImage dhall;
PImage library;


// variable used to track each frame in the players sprite sheet
int playerFrames;
int allTiles;
String prompt[];
int sc6;

// keeps track of the days and weeks of the semester
int days = 1;
int maxDays = 8;
int weeks = 1;
int maxWeeks = 16;

// tracks the amount of acounts you made in a day
int actions = 0;

// stats that the player will change on their own during the game
int intelligence = 0;
int happiness = 0;
int health = 0;

//font for start screen
PFont title;

int screensizeX,screensizeY,stage;

void setup(){
 size(750,750);
 
  playerFrames = 24;
 // Array used to loop through sprite animations
  playerImages = new PImage[playerFrames];
 
 // Tiles for the map
  allTiles = 486;
  
  //different text that can appear before a battle 
  prompt = new String [6];
  prompt[0] = "Your teacher suprised you with a pop quiz";
  prompt[1] = "You have a test today";
  prompt[2] = "Your have to work on your project";
  prompt[3] = "Your homework is due today";
  prompt[4] = "Your project is due today";
  prompt[5] = "You have to complete your finals!!";
 
 /* for(int i = 0; i < allTiles; i++){
  mapTiles[i] = loadImage("Tiles/tile_" + nf(i,2) + ".png");
  }
 supposed to be a for loop that traverses through all images of the tileset, doesnt work
  */
  
  mapTiles = new PImage[3];
  
  mapTiles[0] = loadImage("maptiles/tile_0036.png");
  mapTiles[1] = loadImage("maptiles/tile_0028.png");
  mapTiles[2] = loadImage("maptiles/tile_0076.png");
 
 
  for(int i = 0;i < playerFrames;i++){
    playerImages[i] = loadImage("penguin-gray/UMBCPENGUIN"+nf(i,2)+".png");
  }
  
  battle = loadImage("BattlePenguin.png");
  enemy1 = loadImage("Test.png");
  socialmap = loadImage("main.png");
  dhall = loadImage("dhall.png");
  library = loadImage("library.png");
  
  p = new player(new PVector(width/2,height/2));
  m = new Map();
  c = new controls();
  scene = new Scene();
  b = new Battle();
  
  sleepButton = new Buttons(665,25,50,25,"sleep",195,140,10);
  eatButton = new Buttons(665,55,50,25,"eat",195,140,10);
  studyButton = new Buttons(665,85,50,25,"study",195,140,10);
  socialButton = new Buttons(665,115,50,25,"social",195,140,10);
  backButton = new Buttons(665,675,50,25,"back",195,140,10);
  contButton = new Buttons(width/2 -50,600,75,50,"continue",195,140,10);
  
  stage = 1; 
}

//holds universal functions and method
// universal meaning that they can apply to most, if not all "stages"
void draw(){
    p.update();
    p.restrict();
    
    sleepButton.update();
    eatButton.update();
    studyButton.update();
    socialButton.update();
    
    backButton.update();
    contButton.update();
    
    c.checkKeys();
     
    background(255,255,255);
    startscreen();
    menuToGame(); 
    battles();
}

// Made to display the starting screen before the actual game

  void startscreen(){
  startscreen = loadImage("UMBCLOGO2.png");
  image(startscreen,0,0,width,height);
 }

// Stage variable keeps track of what is displayed on the screen, When the value changes so is the display

void menuToGame(){
   if(stage == 1){
    textAlign(CENTER);
    textSize(25);
    text("SchoolLife",width/2,height- 35);
    text("press any button to start!",width/2,height-5);
    if(keyPressed == true){
      stage = 2;
    }
  }
  
 // when the stage variable equals 2, the background changes, the map ,the player and other assets are displayed 
 // acts as the main stage 
 // gives player the options to choose four differnt actions
   if(stage == 2){
    background(135,206,235);
    scene.display();
    m.loadMap("main.json");
    sleepButton.display();
    eatButton.display();
    studyButton.display();
    socialButton.display();
    stats();
    timePassed();
    
  }
  
  // the stage that appears when choosing to study 
  if(stage == 3){
   // background(255,0,255);
   image(library,0,0,width * 1.8,height  * 1.8);
    p.display(m.mapPosition);
    stats();
    backButton.display();
    timePassed();
   }
  
  // stage that appears when choosing to eat
   if(stage == 4){
   // background(115,0,255);
   image(dhall,0,0,width * 1.8,height  * 1.8);
    p.display(m.mapPosition);
    stats();
    backButton.display();
    timePassed(); 
  }
  
  // stage that appears when choosing to socialize
  if(stage == 5){
   // background(510,90,30);
    image(socialmap,0,0,width * 1.8,height  * 1.8);
    // scene.display();
    p.display(m.mapPosition);
    stats();
    backButton.display();
    timePassed();
  }
  
  // different prompts appear on before different battles
  if(stage == 6 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
  text(prompt[0],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
 
  /* the stage numbers appear random but they are those number because the game 
  will most likely not reach that amount of stages and 
  the 0's correspond with the prompt array
  */
  
 if(stage == 106 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    text(prompt[1],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
      
      if(stage == 1006 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    text(prompt[2],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
      
      if(stage == 10006 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    text(prompt[3],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
     
       if(stage == 100006 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    text(prompt[4],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
      
       if(stage == 1000006 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    text(prompt[5],width/2,height/2);
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
      
    //the intended purpose for this is for the screen to look crazy and random  
      if(stage == 100000006 ){
    background(0,0,0);
    textSize(40);
    fill(255,255,255);
    for(int i = 0; i < prompt.length; i++){
     text(prompt[int(random(i))],width/2,height/2);
   }
    textSize(16);
    stats();
    timePassed();
    contButton.display();
    contButton.isClicked();
      }
      
      
  if(stage == 7){
  background(200,32,1);
  stats();
 
  b.display();
  b.update();
  b.attack();
  }
  
  if(stage == 1000){
    background(255,255,255);
   textSize(24);
   fill(0);
   text("Congratulations you survived your 1st semester ",width/2,height/2);
  }
  
  if(stage == 1001){
    background(255,255,255);
   textSize(32);
   fill(0);
   text("You lost because your intelligence too low make sure to study",width/2,height/2);
   text("make sure to study", width/2 , height/2 + 40);
  }
  
  if(stage == 1002){
    background(255,255,255);
   textSize(32);
   fill(0);
   text("You lost because your not happy",width/2,height/2);
   text("mental health is important",width/2,height/2 + 40);
  }
  
  if(stage == 1003){
    background(255,255,255);
   textSize(22);
   fill(0);
   text("You lost because you're unhealthy,make sure to take care of yourself",width/2,height/2);
  }
}

//function made to choose when different battles occurs, feels random for the player
void battles(){
  
   if(days == 5 && weeks == 1  ){
    stage = 6;
    days++;
   }
   
     if(days == 2 && weeks == 2  ){
    stage = 106;
    days++;
   }
    if(days == 3 && weeks == 3  ){
    stage =1006;
    days++;
   }
   
     if(days == 3 && weeks == 4  ){
    stage = 106;
    days++;
   }
   
     if(days == 4 && weeks == 5  ){
    stage = 6;
    days++;
   }
   
     if(days == 1 && weeks == 6  ){
    stage = 1006;
    days++;
   }
   
   if(days == 1 && weeks == 7 ){
    stage = 1006;
    days++;
   }
   
     if(days == 4 && weeks == 7  ){
    stage = 100006;
    days++;
   }
   
  
  if(days == 1 && weeks == 8 ){
    stage = 100006;
    days++;
   }
   
   if(days == 5 && weeks == 8 ){
    stage = 100006;
    days++;
   }
   
   if(days == 1 && weeks == 9){
    stage = 1006;
    days++;
   }
   
   if(days == 3 && weeks == 9 ){
    stage = 100006;
    days++;
   }
   
   if(days == 1 && weeks == 10){
    stage = 6;
    days++;
   }
   
    if(days == 4 && weeks == 10){
    stage = 100006;
    days++;
   }
   
    if(days == 2 && weeks == 11){
    stage = 106;
    days++;
   }
   
    if(days == 4 && weeks == 12){
    stage = 10006;
    days++;
   }
   
    if(days == 6 && weeks == 12){
    stage = 106;
    days++;
   }
   
    if(days == 2 && weeks == 13){
    stage = 1006;
    days++;
   }
   
    if(days == 4 && weeks == 13){
    stage = 6;
    days++;
   }
   
   
    if(days == 1 && weeks == 14){
    stage = 10006;
    days++;
   }
   
    if(days == 5 && weeks == 14){
    stage = 106;
    days++;
   }
   
    if(days == 1 && weeks == 15){
    stage = 1000006;
    days++;
   }
   
   if(days == 3 && weeks == 15){
    stage = 1000006;
    days++;
   }
   
  if(days == 5 && weeks == 15){
    stage = 100000006;
    days++;
   }      
}
  
// functions controls what the actions of certain buttons due as well as keeping track of time in the semester 
void timePassed(){
  textSize(32);
  fill(0);
  text("Day: " + days, 60, 650);
  text("Week: " + weeks, 60, 700);
  
  if(actions >= 4){
    days += 1;
    actions = 0;
  }
   
  textSize(16);
  if(days == maxDays){
    weeks  += 1;
    days = 1;
  }
  
  if(weeks == maxWeeks){
    stage = 1000;
  }
  
  
  if(sleepButton.isClicked()){
     actions = 4;
     health += 3;
  }
  
  if(studyButton.isClicked()){
    actions ++;
    stage = 3;
    intelligence += 5;
    happiness -= 4;
    health -= 2;
  }
  
    if(eatButton.isClicked()){
    actions ++;
    stage = 4;
    health += 10;
    happiness += 1;
  }
  
   if(backButton.isClicked()){
    stage = 2;
   }
   
   
   if(contButton.isClicked()){
     stage = 7;
   }
   
   if(socialButton.isClicked()){
     actions ++;
     happiness += 10;
     intelligence -= 5;
     stage = 5;
   }
   
}

void stats(){
  
  text("Intelligence",60,50);
  text("Happiness",60,100);
  text("Health",60,150);
  
  fill(100,10,100);
  rect(25,15,intelligence,20);
  
 // fill(0);
  fill(255,10,10);
  rect(25,65,happiness,20);
  
 // fill(0);
  fill(10,255,10);
  rect(25,115,health,20);
  
  if(intelligence >= 100){
    intelligence = 100;
  }
  
  if(health >= 100){
    health = 100;
  }
  
  if(happiness >= 100){
    happiness = 100;
  }
  // game end when the stats drop below zero
  if(weeks >= 3 && intelligence <= 0){
    stage = 1001;
  }
  
  if(weeks >= 3 && happiness <= 0){
    stage = 1002;
  }
  
  if(weeks >= 3 && health <= 0){
    stage = 1003;
  }
  
}



/*
class made for the character the player plays the game as. Involves all functions for the player
*/

class player{
  PVector position;
  float delta;
  float x,y,w,h;
  int currentFrame, loopFrames, offset; //tracks the current frame of the sprite and updates when going in a certain direction
  
  player(PVector iposition){
    //keeps track of the players x and y position
    position = iposition;
    delta = 3.5;
   
    w = 32;
    h = 32;
    currentFrame = 0;
    loopFrames = 6;
    offset = 0;
  }
  
  
  void display(PVector screenPosition){
    image(playerImages[currentFrame + offset], position.x - screenPosition.x , position.y - screenPosition.y);
  }
  
  void moveUp(){
    position.y += delta * -1;
    // the offset variable corresponds with the image value in the sprites folder 
    offset = 0;
  }
   void moveDown(){
    position.y += delta;
    offset = 12;
  }
   void moveLeft(){
    position.x += delta * -1;
    offset = 18;
  }
   void moveRight(){
    position.x += delta;
    offset = 6;
  }
  
  //sets a boundary for the player 
  void restrict(){
    if(position.y <= 0){
      position.y = 0;
    }
    if(position.y >= height){
      position.y = height;
    }
    
    if(position.x >= width ){
      position.x =  width ;
    }
    
    if(position.x <= 0){
      position.x = 0;
    }
    
  }
  
  void update(){
    currentFrame++;
    if(currentFrame == loopFrames){
      currentFrame = 0;
    }
  }
  
}


class Map{
  int sizeX, sizeY;
  int tileW, tileH;
  int tiles[];
  
  PVector mapPosition;
  
  
  Map(){
    sizeX = 50;
    sizeY = 50;
    tileW = 16;
    tileH = 16;
    
    tiles = new int[sizeX * sizeY];  
    for(int i = 0; i < tiles.length; i++){
      tiles[i] =int(random(mapTiles.length));
    }
    
    mapPosition = new PVector(0,0);
  }
  
  void display(PVector screenPosition){
    for(int i =0; i < tiles.length;i++){
       image(mapTiles[tiles[i]],((i%sizeX)*tileW) + (mapPosition.x - screenPosition.x),((i/sizeX)*tileH) + (mapPosition.y - screenPosition.y));
    }
  }
  
  // Map Position moves in the opposite direction of the player
  
  void moveUp(float delta){
    mapPosition.y += delta ;
  }
   void moveDown(float delta){
    mapPosition.y += delta * -1;
  }
   void moveLeft(float delta){
    mapPosition.x += delta ;
  }
   void moveRight(float delta){
    mapPosition.x += delta * -1;
  }
  
  //adds boundaries the tile set and keeps the background colors off the screen
  int leftBoundary(){
    return int(mapPosition.x);
  }
  
  int rightBoundary(){
    return int(mapPosition.x + (sizeX * tileW));
 }
  
  int upperBoundary(){
    return int(mapPosition.y);
  }
  
  int lowerBoundary(){
    return int(mapPosition.y + (sizeY * tileH));
  }
  
  //meant to load tileset maps from JSON files 
  void loadMap(String fname){
    JSONObject objMaster = loadJSONObject(fname);
    JSONArray array = objMaster.getJSONArray("tilesets");
    JSONObject objTile;
    
    for(int i = 0; (i < array.size()) && (i < tiles.length); i ++ ){
      objTile= array.getJSONObject(i);
      tiles[i] = objTile.getInt("firstgid");
    }
    
    
  }
  
  
  
  
}

class controls{
  
  controls(){
    
  }
  
  void checkKeys(){
   
    
    if(keyPressed){
     
    /*only made so that we can test out functions involving battles 
    and demonstrative purposes
    */
    
       if(key == '0'){
     stage = 1002;
      }
      
       if(key == '9'){
     stage = 1000;
      }
      
     if(key == 'l'){
        intelligence = 100;
        happiness = 100;
        health = 100;
        weeks ++;
      }
      
    
      if(key == 'm'){
        stage =6;
      }
      
       if(key == 'p'){
        days = maxDays;
        weeks = maxWeeks;
      }
      
      if(key == 'w'){
        p.moveUp();
      scene.centerPlayer(p);
      scene.mapBounds(m);
      }
      
      if(key == 's'){
        p.moveDown();
       scene.centerPlayer(p);
        scene.mapBounds(m);
      }
      
      if(key == 'a'){
        p.moveLeft();
       scene.centerPlayer(p);
       scene.mapBounds(m);
      }
      
      if(key == 'd'){
        p.moveRight();
       scene.centerPlayer(p);
        scene.mapBounds(m);
      }
      
    }
    
  }
  
}

class Battle {
  //keeps track of the different conditions that can affect the way a battle plays out ( value of the week and the stats)
  int AT = 0;
  //Keeps track of the players and oppenents health 
  int[] hp = new int[2];
  
  Battle(){
    hp[0] = 2000;
    hp[1] = 3000;
  }
  
  void display(){
     textSize(30);
     fill(255,255,255);
     text("Finish your 'work' before it beats you!",width/2 - 35,100);
     text("Press 1 to attack!",width/2 - 35,150);
     image(battle,0,height/2,200,220);
     image(enemy1,325,75,600,600);
     
     //health bar for the player
      fill(0);
     textSize(15);
     rect(25,600,250,25);
     text(hp[0],250,644);
     fill(0,255,0);
    rect(25,600,hp[0]/8,25);
    
    //health bar for the enemy
    fill(0);
     rect(475,600,250,25);
    text(hp[1],700,644);
    fill(0,255,0);
    rect(475,600,hp[1]/12,25);
  }
  
  void update(){
    //The battles are essentially time trials 
     AT = int(random(1,15));
  switch(AT){
    case 1:
    if(weeks == 1){
      hp[0] -= int(random(20,25));
    }
    //Makes "test taking" easier if the intelligence stat is high 
    if(intelligence >= 10){
      hp[0] -= int(random(0,10));
    }
      break;
    case 2:
      if(weeks == 2){
      hp[0] -= int(random(45,65));
      }
      
      // the requirement for the easier "test" becomes higher as the weeks get higher
       if(intelligence >= 30){
      hp[0] -= int(random(20,25));
    }
      
      break;
    case 3:
      if(weeks == 3 || weeks == 4){
      hp[0] -=int(random(100,125));
      }
      // more stats are included in the requirement so that they feel as important
        if(intelligence >= 30  && happiness >= 20){
          hp[0] -= int(random(45,65));
      }
    
      break;  
      case 4:
        if(weeks == 5 || weeks == 6){
      hp[0] -=int(random(100,125));
      }
        if(intelligence >= 40  && happiness >= 20){
          hp[0] -= int(random(45,65));
      }
      break;
      case 5:
      
        if(weeks == 7 || weeks == 8){
      hp[0] -=int(random(200,250));
      }
        if(intelligence >= 60  && happiness >= 30 && health >= 10){
          hp[0] -= int(random(100,125));
          boostAttack();
      }
      break;
      case 6:
      
        if(weeks == 9 || weeks == 10){
      hp[0] -=int(random(350, 375));
      }
      
      if(intelligence >=  70 && happiness >= 35 && health >= 25){
          hp[0] -= int(random(200,275));
          boostAttack();
      }
      break;
      case 7:
         if(weeks == 11|| weeks == 12){
      hp[0] -=int(random(375, 400));
      }
      
      if(intelligence >=  80 && happiness >= 40 && health >= 25){
          hp[0] -= int(random(350,375));
          boostAttack();
      }
      break;
      case 8:
         if(weeks == 13 || weeks == 14){
      hp[0] -=int(random(400, 425));
      }
      
      if(intelligence >=  85 && happiness >=  50 && health >= 35){
          hp[0] -= int(random(375,400));
          boostAttack();
      }
      case 9:
         if(weeks == 15){
      hp[0] -=int(random(500, 550));
      }
      
      if(intelligence >=  90 && happiness >= 55 && health >= 45){
          hp[0] -= int(random(100,125));
          boostAttack();
      }
      
  }
  
  if(hp[0] <= 0){
    //consequence for "failing a test" is to have your stats reduced severly
    intelligence -= 20;
    happiness /= 2;
    health -= 10;
    stage =2;
    
    // resets both players and oppenents health at the end of a test
    hp[0] = 2000;
    hp[1] = 3000;
  }
  
  if(hp[1] <= 0){
    //take the player back to the main game at the end of a test\
   stage = 2;
   happiness += 5;
   
   hp[1] = 3000;
   hp[0] = 2000;
  }
  
  }
  
  // reduces the oppenents health by 200 points every time the 1 button us pressed
  void attack(){
    if(keyPressed){
      
       if(key == '1'){
      hp[1] -= 200;
    }
    
  }
 }
 
 //Function used to reward player for having high stats
 void boostAttack(){
   if(key  == '1'){
     hp[1] -= 400;
     
     if(weeks > 10){
       hp[1] -= 500;
     }
     if(weeks > 12){
       hp[1] -= 700;
     }
   }
 }
}

class Buttons {

  PVector Pos = new PVector(0,0);
  float buttonW = 0;
  float buttonH = 0;
  color buttonC;
  String text;
  Boolean Pressed = false;
  Boolean Clicked = true;
  
  Buttons(int x, int y,int w, int h, String t,int r, int g, int b){
    Pos.x = x;
    Pos.y = y;
    buttonW = w;
    buttonH = h;
    buttonC = color(r,g,b);
    text = t;  
  }
  
  void update(){
    // checks if the left mouse button is pressed
    if(mousePressed == true && mouseButton == LEFT && Pressed == false)
{ 
   Pressed = true;
   // makes sure that the mouse is clicking the area that the button is displayed
   if (mouseX >= Pos.x && mouseX <= Pos.x + buttonW && mouseY >= Pos.y && mouseY <= Pos.y + buttonH) 
   { 
     Clicked = true;
   }
}
   else
   {
     Clicked = false;
    }
    
    if(mousePressed != true){
      Pressed = false;
    }
    
   } 
  
  
   void display(){
     fill(buttonC);
     rect(Pos.x,Pos.y,buttonW,buttonH);
     
     fill(0);
     textAlign(CENTER,CENTER);
     // displays the text in the center of the box 
     text(text,Pos.x + (buttonW /2), Pos.y + ( buttonH /2));
   }
 
 // function used in if statements to check if the buttons were clicked
   boolean isClicked(){
     return Clicked;
   }


}

class Scene 
{
  PVector position;
  
  Scene(){
    position = new PVector(0,0);
  }
    
    void display(){
       m.display(position);
       p.display(position);
    }
    //centers the player as the screen moves along with the player
    void centerPlayer(player p){
      position.x = p.position.x - width/2;
      position.y = p.position.y - height/2;
    }
    
   // the tileset has a boundary that covers the background 
    void mapBounds(Map m){
      
      if(position.x < m.leftBoundary()){
        position.x = m.leftBoundary();
      }
      
       if(position.y < m.upperBoundary()){
        position.y = m.upperBoundary();
      }
      
       if(position.x > m.rightBoundary() - width) {
        position.x = m.rightBoundary() - width;
      }
      
       if(position.y > m.lowerBoundary() - height){
        position.y = m.lowerBoundary() - height;
      }
    }
  
}
