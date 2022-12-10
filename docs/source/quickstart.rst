Quickstart
=====

Mandatory
--------

You must use the following code, **or aDL will not work** 
.. code-block:: console
  **#include "[aDL dir]/aDL.h"** // import aDL
  
  int main(){
    **adl::init();** // initializing aDL
    // do your stuff
    **adl::quit();** // quitting aDL
    return 0;
  }
  
Example
--------

.. code-block:: console
  **#include "[aDL dir]/aDL.h"** // import aDL
  
  void lowerVolumeTo10(){
    adl::sound::setVolume(10); // set the global volume to 10
  }
  
  int main(){
    **adl::init();** // initializing aDL
    
    adl::assignFunctionToKey(SDL_SCANCODE_F, lowerVolumeTo10); // set the key F to execute the function lowerVolumeTo10
    
    adl::Sprite buddy("buddy.png buddy_runnning.bmp buddy_running2.jpeg"); // creating the buddy Sprite with 3 costumes
    buddy.scale(2, 0.5); // scaling buddy Sprite vertical size by 2 and its horizontal size by 0.5
    
    adl::Sound music("music.mp3"); // creating a Sound variable with the music.mp3 file
    music.play();
    
    while(adl::window::isOpen()){
      buddy.draw(); // render the buddy
      buddy.nextCostume(); // set the costume (texture displayed) to the next one
      adl::render::update(); // update the window (strongly recommended to be put at the end of your gameloop)
    }
    
    **adl::quit();** // quitting aDL
    return 0;
  }
