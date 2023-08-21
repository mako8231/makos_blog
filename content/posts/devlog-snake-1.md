+++
title = "Devlog Snake 1"
date = "2023-08-21T09:36:42-04:00"
author = "'Mako' Muraoka"
authorTwitter = "lightsigel" #do not include @
cover = "Documenting my SDL studying"
tags = ["SDL2", "SDL", "C", "programming", "studying", "snake game"]
keywords = ["snake", "SDL", "mako8231", "mako", "lightsigel", "rallyrio"]
description = "describing my first day working on snake game project written in C"
showFullContent = false
readingTime = false
hideComments = false
color = "" #color from the theme settings
+++

## Devlog - Snake Game (under construction)

I'm pretty realy lazy when it comes to trying to follow a step-by-step process to learn any technology. I gave learning SDL2 a shot, and even though the theorical material helped me intially to understand the core concepts about the framework, I couldn't really stick to following every single day. 

Back into 2018, I finally got on track when I'm learning Godot and taking initiative to make projects to my own (even with poor programming practices) precisely **just making. Projects.**

That's why I got the initiative to write down for this blog, and documenting my progress.

Every project using SDL that I'll be working on it's avaible on my github, clicking [here](https://github.com/mako8231/SDL_Projects).

Now it comes the fun part, I'll take some rules:
* Making the project with pure C;
* Making my own sprites;
* Documenting every project;

And, like I said when using pure C, I'll take focus on structured programming, there's no particular reason behind of this, I'm used to program with OOP, and never took initiative to make a solid project using this paradigm.

Also, take a look at my main.c, isn't my baby cute?

```c
#include <stdio.h>
#include <stdlib.h>
#include <SDL2/SDL.h>
#include "game.h"


int main(int argc, char* argv[]) {
    Game game;
    game_init(&game, "Snake Game", SDL_WINDOWPOS_CENTERED,
    SDL_WINDOWPOS_CENTERED, 640, 480, 0);

    //Clean up SDL
    while (game.running){
        game_render(&game);
        game_update(&game);
        game_handle_events(&game);
    }
    SDL_DestroyWindow(game.window);
    SDL_Quit();
    return 0;
}

```
