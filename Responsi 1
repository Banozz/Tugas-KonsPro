// Simple turn based game
// Written by Ibrahim Nur Huda/ L0122076
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <math.h>

// Deklarasi variabel
int *hp_pointer;
int *hp2_pointer;

// Deklarasi pointer health
int health = 300;
int health2 = 100;

int *hp_pointer = &health;
int *hp2_pointer = &health2;

// Deklarasi array untuk attack bot
int dmg2[] = {10, 15, 25, 35};
int x;

// Deklarasi function untuk pengurangan pointer
void damage(int *hp_pointer, int dmg);
void damage2(int *hp2_pointer,int dmg2);

// Function untuk rand point damage
int d;
int light(int d){
    srand(time(NULL));
    d = 18 + rand() % 10;
    return d;
}

int medium(int d){
    d = 40;
    return d;
}

int heavy(int d){
    srand(time(NULL));
    d = 35 + rand() % 36;
    return d;
}

// Function main
int main(){
    
    int opt; // Untuk opsi Main Menu
    int move; // Untuk opsi serangan
    char inChoice; // Untuk opsi informasi
    int reattempt; // Untuk opsi coba lagi

    Menu: // Main menu interface
    puts("=================================================================================");
    puts("Welcome to Monster Arena!");
    puts("(1) Player Versus Enemy (PvE)");
    puts("(2) Attack Informations");
    puts("(3) Exit");
    puts("=================================================================================");
    printf("What do you want to do: "); 
    scanf("%d", &opt);
    system("cls");

    doPvE: // Player Vs Enemy
    if(opt == 1) {
        *hp_pointer = 300;
        *hp2_pointer = 100;
        do{
        puts("=================================================================================");
        puts("It's your turn!");
        printf("Your health now: %d\n", health2);
        for(int i = 0; i <= health2 / 2; i++){
            printf("+");
        }
        puts("\n=================================================================================");
        puts("Choose your attack!");
        puts("(1) Light Attack");
        puts("(2) Medium Attack");
        puts("(3) Heavy Attack");
        puts("(4) Heal");
        puts("(5) Run away");
        printf("Which move do you want: "); scanf("%d", &move);// Input skill
        system("cls");

        switch(move){ // Penentu damage per skill
            case 1:
                damage (hp_pointer, light(d));
            break;
            case 2:
                damage (hp_pointer, medium(d));
            break;
            case 3:
                damage (hp_pointer, heavy(d));
            break;
            case 4:
                damage2 (hp2_pointer, -40);
            break;
            case 5:
                goto Menu;
            default:
                printf("Input invalid\n");
                puts("Turn skipped.");
        }

        // Menu setelah mengalahkan enemy
        if(health <= 0) {
            health = 0;
            puts("\nYou've defeated your enemy!");
            puts("What do you wanna do?");
            puts("(1) I want more >:)");
            puts("(2) Go back to main menu.");
            puts("(3) Exit");
            printf("Your choice: "); scanf("%d", &reattempt);

            switch(reattempt){ // Switch untuk pilihan reattempt
                case 1:
                system("cls");
                    goto doPvE; // Fight ulang
                break;
                case 2:
                    system("cls");
                    goto Menu;  // Kembali ke main menu
                break;
                case 3:
                    return 0;
                default:
                    system("cls");
                    puts("Input invalid.");
                    goto Menu;
            }
        }

        // Enemy attacking system
        puts("\n================================================================================= \nIt's your enemy's turn");
        
        printf("Your enemy's health: %d/300\n", health);
        for(int i = 0; i <= health / 4; i++){
            printf("x");
        }
        srand(time(NULL));
        x = rand() % 4;
        puts("");
        printf("\nYour enemy deal %d damages!\n", dmg2[x]);
        damage2 (hp2_pointer, dmg2[x]);


        // Menu setelah dikalahkan oleh enemy
        if(health2 <= 0){
            health2 = 0;
            puts("\nYou've been defeated.");
            puts("What do you wanna do?");
            puts("(1) Try again.");
            puts("(2) Go back to main menu.");
            puts("(3) Exit");
            printf("Your choice: "); scanf("%d", &reattempt);

            switch(reattempt){ // Switch untuk pilihan reattempt
                case 1:
                    system("cls");
                    goto doPvE;   // Fight ulang
                break;
                case 2:
                    system("cls");
                    goto Menu;    // Kembali ke main menu
                break;
                case 3:
                    system("cls");
                    return 0;     // Untuk memberhentikan program
                default:
                    system("cls");
                    puts("Input invalid.");
                    goto Menu;
            }
        }

        } while (health >= 0 || health2 >= 0);
    }
    
    // Untuk pilihan Attacking Info
    else if(opt == 2){
        info :
        puts("=================================================================================");
        puts("Attack Informations:");
        puts("(1) Light Attack deals small, quick, and consistent damage");    
        puts("(Deals 18 - 27 damages)\n");
        puts("(2) Medium Attack deals moderate, normal, and constant damage");
        puts("(Deals 45 damages)\n");
        puts("(3) Heavy Attack deals heavy, slow, and inconsistent attack");
        puts("(Deals 35 - 70 damage point to the enemy)\n");
        puts("(4) Heal, Regenerate 40 hp points");
        puts("(5) Run away, running away from your opponent and immediately return to main menu");
        puts("(-) If you misstype your attack, your turn will be dismissed");
        puts("=================================================================================");
        puts("Go back to main menu?");
        printf("( y / n ) | Your choice : "); 
        scanf("%s", &inChoice);
        if(inChoice == 'y' || inChoice == 'Y'){
            system("cls");
            goto Menu;
        } else if(inChoice == 'n'){
            system("cls");
            goto info;
        } else {
            system("cls"); 
            goto info; 
        }  
     
    } else if(opt == 3){// Untuk pilihan exit 
        return 0;
    }  
}

// Untuk pengurangan health
void damage(int *hp_pointer, int dmg){
    *hp_pointer = *hp_pointer - dmg;
}

void damage2(int *hp2_pointer, int dmg2){
    *hp2_pointer = *hp2_pointer - dmg2;
}

