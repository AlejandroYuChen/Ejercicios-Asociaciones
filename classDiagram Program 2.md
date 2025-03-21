```mermaid
classDiagram
    class Auto {
        - string nombre
        - string modelo
        - bool disponible
        + Auto(string p, string m)
        + ~Auto
        + string getPlaca() const
        + string getModelo()
        + bool estaDisponible()
        + bool rentar()
        + bool devolver()
    }

    class Cliente {
        - int id
        - string nombre
        + Cliente(int i,string n)
        + ~Cliente() 
        + int getId() const
    }

    class Contrato {
        - Cliente* cliente
        - Auto* rentado
        - int dias
        + Contrato(Cliente* c, Auto* a, int d)
        + ~Contrato()
    }

    class AgenciaRenta {
        - string nombre
        - vector<Auto*> autos
        - vector<Cliente*> clientes
        + AgenciaRenta(string n)
        + ~AgenciaRenta()
        + void agregarAuto(Auto* autoPtr)
        + void agregarCliente(Cliente* clientePtr)
        + void mostrarInfo() const
    }

    AgenciaRenta o-- Auto
    AgenciaRenta o-- Cliente
    Auto --> Contrato
    Cliente --> Contrato
```
