# repoprueba
#prueba de programación orientada objeto
from  datetime import datetime
from math import acos, cos, sin, radians
c=0
while c!=2:
    opc=int(input("1.- Registrarse\n2.-Comenzar carrera\n"))
    i=1 
    auto="Apagado"
    velocidad=0
    if opc ==1 and c==0:
        nombre=input("Ingrese Nombre y Apellido: \n")
        rut=input("Ingrese rut:\n")
        modelo=input("Ingrese modelo del auto:\n")
        patente=input("Ingrese N° patente:\n")
        c=1
    else:
        print("primero debe registrarse ")      
    if opc == 2 and c==1:
        lugar1=input("Ingrese el lugar de destino:\n")
        lon1=radians(float(input("Ingrese la longitud:\n")))
        lat1=radians(float(input("Ingrese la latitud:\n")))
        lugar2=input("Ingrese el punto de partida:\n")
        lon2=radians(float(input("Ingrese la longitud:\n")))
        lat2=radians(float(input("Ingrese la latitud:\n")))
        
        while i!=0:
            if opc == 2:
                print("1. Encender auto\n2. Acelerar\n3. Frenar\n4. Apagar auto\n5. Mostrar datos\n6. salir\n7. ver fecha y hora \n")    
                opc2=int(input("Ingrese opcion\n"))
            if opc2 == 1:
                auto="Encendido"
                print("**************************************")
                print("Auto encendido")
                print("**************************************")
            if opc2 == 2:
                if auto != "Encendido":
                    print("**************************************")
                    print("No se puede acelerar, auto apagado")
                    print("**************************************")
                else:
                    velocidad+=10
                    print("**************************************")
                    print("Velocidad actual: ",velocidad,"km/h")
                    print("**************************************")
            if opc2 == 3:
                if velocidad==0:
                    print("**************************************")
                    print("el auto esta detenido")
                    print("**************************************")
                else:
                    velocidad-=10
                    print("************************************")
                    print("viajas a ",velocidad," km/h")
                    print("************************************")
            if opc2 == 4:
                if velocidad !=0:
                    print("************************************")
                    print("frena primero para poder apagar el auto")
                    print("**************************************")
                else:
                    auto="Apagado"
                    print("********************************")
                    print("**********Auto apagado**********")
                    print("********************************")
            if opc2 == 5:
                print("los datos del conductor del vehiculo son :")
                print("**************************************")
                print("Nombre: ",nombre,"\nRut: ",rut,"\nModelo: ",modelo,"\nPatente: ",patente)
                print("**************************************")
            if opc2 == 6:
                if velocidad > 0:
                    print("**************************************")
                    print("llamando a emergencia,no puedes salir mientras el auto este en movimiento")
                    print("**************************************")
                else:
                    print("Saliste del auto")
                i=0
                c=2
            if opc2 == 7:
                import datetime
                print(datetime.datetime.now())
                print("**************************************")
        dreco=6371.0 * acos(sin(lat1) * sin(lat2) + cos(lat1) * cos(lat2) * cos(lon1 - lon2))
        pago=dreco*350
        print("Distancia recorrida: ",dreco,"km\nMonto a pagar: $",pago)


         
