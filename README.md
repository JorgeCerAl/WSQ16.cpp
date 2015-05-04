# WSQ16.cpp
Read .txt


/*
 *  #WSQ16
 *  Created by George.16 on 4/23/15.
 *  Copyright (c) 2015 George.16. All rights reserved.
 *  Main: Read text files from C++
 *  #TC1017
 *  Referencia: xxxxxxxxxxxxxxxxxxx
 *
 */
#include <iostream>
#include <fstream>
#include <string>
#include <cstdlib>

using namespace std;

int main () {
    int llanos = 0, coco = 0;
    double sumaq = 0, sumaw = 0, sumae = 0;
    string linea;
    
    ifstream docum ("93cars.txt");
    if (docum.is_open())
    {
        while ( getline (docum,linea) )
        {
            if(coco ==0){
                string city = linea.substr(37,4);
                sumaq = atof(city.c_str()) + sumaq;
                
                cout << city << endl;
            
                string highway = linea.substr(42,4);
                sumaw = atof(highway.c_str()) + sumaw;
            
                string precio = linea.substr(47,4);
                sumae = atof(precio.c_str()) + sumae;
            }
            llanos = llanos + 1;
            coco = (llanos % 2);
            
            
        }
        docum.close();
        
        cout << "Average gas mileage in city is "<< sumaq/llanos << " MPG"<< endl;
        cout << "Average gas mileage on highway is "<< sumaw/llanos << " MPG"<< endl;
        cout << "Average midrange price of the vehicles is "<< sumae/llanos << endl;
    }
    
    else cout << "Unable to open file";
    
    return 0;
}
