# include <iostream>
#include <string>
using namespace std;

//crear estructura trabajador con los siguientes campos: nombre, cedula, ocupacion y edad
struct trabajador {
    string nombre, cedula,ocupacion;
    int edad;    
};

//declarar un areglo de registros
trabajador arraytrabajadores[300];

//implementar las funciones
//guardar datos de un trabajador
void GuardarTrabajador(){

    cout<<"Ingrese los datos del trabajador: "<<endl;
    for(int i=0; i<4; i++){
        cout<<"Trabajador "<<i+1<<endl;
        cout<< "Ingrese el nombre del trabajador: ";
        cin>> arraytrabajadores[i].nombre;
        cout<< "Ingrese la cedula del trabajador: ";
        cin>> arraytrabajadores[i].cedula;
        cout<<"edad del trabajador: ";
        cin>> arraytrabajadores[i].edad;
        cout<<"ocupacion del trabajador: ";
        cin>> arraytrabajadores[i].ocupacion;
    }
}


//mostrar datos del areglo de trabajadores
void mostrarTrabajadores(){

    cout<<"datos de los trabajadores: "<<endl;
    cout<<"nombre\tcedula    \tedad\tocupacion"<<endl;
for(int i=0; i<4; i++){
    cout<<arraytrabajadores[i].nombre<<'\t'<<arraytrabajadores[i].cedula<<'\t'<<arraytrabajadores[i].edad<<'\t'<<arraytrabajadores[i].ocupacion<<endl;

    }
}

//funcion ordenar acendentemente

void OrdenarAscendenteEdadTrabajador(){

    trabajador arraytemp[300];
    cout<<"lista ordenada por edad: "<<endl;
    for(int i=0; i<4; i++){
        for(int j=0; j<4; j++){
            if(arraytrabajadores[i].edad < arraytrabajadores[j].edad){
                arraytemp[i].nombre = arraytrabajadores[j].nombre;
                arraytemp[i].cedula = arraytrabajadores[j].cedula;
                arraytemp[i].edad = arraytrabajadores[j].edad;
                arraytemp[i].ocupacion = arraytrabajadores[j].ocupacion;

                arraytrabajadores[j].nombre = arraytrabajadores[i].nombre;
                arraytrabajadores[j].cedula = arraytrabajadores[i].cedula;
                arraytrabajadores[j].edad = arraytrabajadores[i].edad;
                arraytrabajadores[j].ocupacion = arraytrabajadores[i].ocupacion;

                arraytrabajadores[i].nombre = arraytemp[i].nombre;
                arraytrabajadores[i].cedula = arraytemp[i].cedula;  
                arraytrabajadores[i].edad = arraytemp[i].edad;
                arraytrabajadores[i].ocupacion = arraytemp[i].ocupacion;


}

        }
    }
}



int main(){
    GuardarTrabajador();
    mostrarTrabajadores();
    OrdenarAscendenteEdadTrabajador();
    return 0;
}

