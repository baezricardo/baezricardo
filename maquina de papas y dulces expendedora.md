#include <iostream>
using namespace std;

int main() {
    // Definición de los productos y sus precios
    string productos[] = {"Papas", "Cacahuates", "Paletas"};
    double precios[] = {18.0, 12.0, 8.0};
    int cantidades[] = {20, 15, 25};
    
    // Mostrar mensaje de bienvenida
    cout << "Bienvenido a la Máquina Expendedora de Dulces" << endl;
    
    // Mostrar el menú de productos, precios y cantidades disponibles
    cout << "Productos disponibles:" << endl;
    for (int i = 0; i < 3; i++) {
        cout << i+1 << ". " << productos[i] << " - $" << precios[i] << " - Cantidad: " << cantidades[i] << endl;
    }
    
    // Solicitar al usuario que seleccione un producto
    int seleccion;
    cout << "Seleccione el número del producto que desea comprar: ";
    cin >> seleccion;
    
    // Verificar selección válida
    if (seleccion < 1 || seleccion > 3) {
        cout << "Selección inválida. Intente nuevamente." << endl;
        return 0;
    }
    
    // Calcular el índice del producto seleccionado en base al arreglo (restar 1)
    int indice = seleccion - 1;
    
    // Verificar disponibilidad del producto seleccionado
    if (cantidades[indice] == 0) {
        cout << "El producto seleccionado está agotado." << endl;
        return 0;
    }
    
    // Solicitar al usuario que ingrese el monto pagado
    double montoPagado;
    cout << "Ingrese el monto pagado ($" << precios[indice] << "): ";
    cin >> montoPagado;
    
    // Verificar si el monto pagado es suficiente
    if (montoPagado < precios[indice]) {
        cout << "Monto insuficiente. La compra no puede ser realizada." << endl;
        return 0;
    }
    
    // Calcular el cambio
    double cambio = montoPagado - precios[indice];
    
    // Actualizar la cantidad disponible del producto seleccionado
    cantidades[indice]--;
    
    // Mostrar el producto seleccionado, el cambio y la cantidad restante
    cout << "Retire su producto: " << productos[indice] << endl;
    cout << "Su cambio: $" << cambio << endl;
    cout << "Cantidad restante de " << productos[indice] << ": " << cantidades[indice] << endl;
    
    return 0;
}
