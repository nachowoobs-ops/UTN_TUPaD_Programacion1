# UTN_TUPaD_Programacion1
#ejercicio 1
continuar = True
while continuar:
    nombre = input("Ingrese su nombre: ")
    if nombre.replace(" ", "").isalpha():
        print("Hola!", nombre)
        break
    else:
        print("Por favor ingrese nombre solo con letras.")

continuar_dos = True
while continuar_dos:
    productos = input("Coloque cuántos productos desea comprar: ")
    if productos.isdigit():
        productos = int(productos)
        if productos > 0:
            break
        else:
            print("La cantidad debe ser mayor a 0.")
    else:
        print("Por favor coloque números enteros positivos.")

total_sin_descuento = 0
total_con_descuento = 0
productos = int(productos)
for i in range(productos):
    print(f"Producto {i + 1}:")

    continuar_tres = True
    while continuar_tres:
        precio = input(f"Coloque el precio del producto {i + 1}: ")
        if precio.isdigit():
            precio = int(precio)
            break
        else:
            print("Por favor coloque el precio correctamente.")

    continuar_cuatro = True
    while continuar_cuatro:
        descuento = input(f"¿Tiene descuento el producto {i + 1}? (S/N): ")
        if descuento.lower() == "s" or descuento.lower() == "n":
            break
        else:
            print("Por favor ingrese S o N.")

    total_sin_descuento += int(precio)
    precio = int(precio)
    if descuento.lower() == "s":
        precio_des = precio - (precio * 0.10)
        print(f"Precio con descuento: {precio_des:.2f}")
        total_con_descuento += precio_des  
    else:
        print(f"Precio sin descuento: {precio}")
        total_con_descuento += precio      

ahorro_total = total_sin_descuento - total_con_descuento
promedio_por_prod = float(total_con_descuento) / productos
print(f"Total sin descuentos: {total_sin_descuento:.2f}")
print(f"Total con descuentos: {total_con_descuento:.2f}")
print(f"Ahorro total: {ahorro_total:.2f}")
print(f"Promedio por producto: {promedio_por_prod:.2f}")
#ejercicio 2
usuario = "alumno"
clave_correcta = "python123"
intentos = 3 
opcion_2 = "0"
while (intentos >= 1):
    usuario_alumno = input("ingrese el usuario: ")
    if usuario_alumno == usuario:
        clave_alumno = input("introduzca la clave: ")
        if clave_alumno == clave_correcta:
            print("ha ingresado correctamente. ")
            break
        else:
            intentos -= 1
            print("clave incorrecta. ")
    else:
        intentos -= 1
        print("usuario incorrecto. ")
        print(f"te quedan {intentos}, intentos. ")
        if intentos == 0:
            print("cuenta bloqueada. ")
while opcion_2 != "4" and intentos != 0:
    print("---1---(Ver estado de inscripción )")
    print("---2---(Cambiar clave y confirmacion) ")
    print("---3---(frase motivacional) ")
    print("---4---(salir del campus) ")
    opcion = input("Eliga la opcion que desea ingresar (1-4): ")
    if opcion.isdigit():
        opcion = int(opcion)
    
        if opcion in (1,2,3,4):
            match opcion:
                case 1:
                    continuar = True
                    while continuar:
                        if opcion == 1:
                            print("estado de inscripcion: (inscripto)")
                            break      
                        
                case 2:
                    nueva_contraseña = input("ingrese la nueva contraseña: ")
                    while nueva_contraseña:
                        confirmacion = input("confirme la contraseña nueva: ")
                        if nueva_contraseña == confirmacion:
                            print("la contraseña se cambio exitosamente. ")
                            clave_correcta = nueva_contraseña
                            break
                        else:
                            print("la contraseña no coincide con la confirmacion. ")
                case 3:
                    print("la disciplina triunfa ante todo.")
                    
                case _:
                    print("hasta luego. ")
                    break
        else:
            print("por favor ingrese un valor correspondiente al menú. ")
#ejercicio 3
lunes_1 = ""
lunes_2 = ""
lunes_3 = ""
lunes_4 = ""
martes_1 = ""
martes_2 = ""
martes_3 = ""
continuar_op = True
while continuar_op:
    nombre_3 = input("introduzca su nombre: ")
    if nombre_3.replace(" ","").isalpha():
        print(f"¡bienvenido {nombre_3}, que desea hacer? ")
        continuar_op = False
    else: 
        print("solo se permite colocar letras. ")
continuar_menu = True
while continuar_menu:
    print("---1---reservar turno. ")
    print("---2--Cancelar turno (por nombre). ")
    print("---3---ver agenda del dia. ")
    print("---4---resumen del general. ")
    print("---5---cerrar sistema. ")
    elegir = input("eliga lo que desea hacer (1-5):")
    if elegir.isdigit():
        elegir = int(elegir)
        if elegir in range (1,6):
            match elegir:
                case 1:
                    continuar__ = True
                    while continuar__:
                        print("elija su dia de reserva: ")
                        reserva = input("1-lunes, 2-martes: ")
                        if reserva.isdigit() and int(reserva) in (1, 2):
                            reserva = int(reserva)
                            continuar__= False
                        else:
                            print("por favor ingrese correctamente para agendar su turno.")
                    continuar_pac = True
                    while continuar_pac:
                        paciente = input("ingrese el nombre del paciente: ").lower()
                        if paciente.replace(" ","").isalpha():
                            continuar_pac = False
                            
                        else:
                            print("solo puede ingresar letras. ")
                    continuar_agenda = True
                    while continuar_agenda:
                        if reserva == 1:
                            if lunes_1 == "":
                                lunes_1 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if lunes_2 == "":
                                lunes_2 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if lunes_3 == "":
                                lunes_3 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if lunes_4 == "":
                                lunes_4 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if lunes_1 != "" and lunes_2 != "" and lunes_3 != "" and lunes_4 != "":
                                print("No hay turnos disponibles para el lunes. ")
                                break
                        if reserva == 2:
                            if martes_1 == "":
                                martes_1 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if martes_2 == "":
                                martes_2 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if martes_3 == "":
                                martes_3 = paciente
                                print("Se ha agendado correctamente ")
                                break
                            if martes_1 != "" and martes_2 != "" and martes_3 != "":
                                print("No se encuentran turnos disponibles para el dia martes. ")
                                break

                case 2:
                    continuar_eliminar = True
                    while continuar_eliminar:
                        print("elija el dia de reserva: ")
                        reserva_dia = input("1-lunes, 2-martes: ")
                        if reserva_dia.isdigit() and int(reserva_dia) in (1, 2):
                            reserva_dia = int(reserva_dia)
                            continuar_eliminar= False
                        else:
                            print("por favor ingrese correctamente para poder eliminar el turno.")
                    continuar_nombre = True
                    while continuar_nombre:
                        nombre_paciente = input("ingrese el nombre del paciente que quiere quitar de la reserva: ").lower()
                        if nombre_paciente.replace(" ","").isalpha():
                            continuar_nombre = False
                            if reserva_dia == 1:
                                if nombre_paciente == lunes_1:
                                    lunes_1 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if nombre_paciente == lunes_2:
                                    lunes_2 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if nombre_paciente == lunes_3:
                                    lunes_3 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if nombre_paciente == lunes_4:
                                    lunes_4 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if  nombre_paciente != lunes_1 and nombre_paciente != lunes_2 and nombre_paciente != lunes_3 and nombre_paciente != lunes_4:
                                    print("No se encuentran turnos agendados con ese nombre. ")
                                    break
                            if reserva_dia == 2:
                                if nombre_paciente == martes_1:
                                    martes_1 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if nombre_paciente == martes_2:
                                    martes_2 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if nombre_paciente == martes_3:
                                    martes_3 = ""
                                    print("Se borro correctamente de la reserva. ")
                                    break
                                if  nombre_paciente != martes_1 and nombre_paciente != martes_2 and nombre_paciente != martes_3:
                                    print("No se encuentran turnos agendados con ese nombre.") 
                                    break
                        else:
                            print("Solo puede ingresar letras. ")
                    
                case 3:
                    if lunes_1 == "":
                        print("Primer turno del dia lunes(libre) ")
                    else:
                        print(f"primer turno del dia lunes: {lunes_1}. ")
                    if lunes_2 == "":
                        print("segundo turno del dia lunes (libre) ")
                    else:
                        print(f"segundo turno del dia lunes: {lunes_2}. ")
                    if lunes_3 == "":
                        print("tercer turno del dia lunes(libre) ")
                    else:
                        print(f"tercer turno del dia lunes: {lunes_3}. ")
                    if lunes_4 == "":
                        print("cuarto turno del dia lunes(libre) ")
                    else:
                        print(f"cuarto turno del dia lunes: {lunes_4}. ")
                    if martes_1 == "":
                        print("primer turno del dia martes (libre). ")
                    else:
                        print(f"primer turno del dia martes: {martes_1}. ")
                    if martes_2 == "":
                        print("segundo turno del dia martes (libre). ")
                    else:
                        print(f"segundo turno del dia martes: {martes_2}. ")
                    if martes_3 == "":
                        print("turno turno del dia martes (libre). ")
                    else:
                        print(f"tercer turno del dia martes: {martes_3}. ")
                    
                case 4 :
                    ocupados_lunes = 0
                    ocupados_martes = 0
                    libres_lunes = 0
                    libres_martes = 0
                    if lunes_1 != "":
                        ocupados_lunes += 1
                    if lunes_2 != "":
                        ocupados_lunes += 1
                    if lunes_3 != "":
                        ocupados_lunes += 1
                    if lunes_4 != "":
                        ocupados_lunes += 1

                    if martes_1 != "":
                        ocupados_martes += 1
                    if martes_2 != "":
                        ocupados_martes += 1
                    if martes_3 != "":
                        ocupados_martes += 1
                    ocupados_semana = (ocupados_lunes + ocupados_martes)
                    print(f"Turnos semanales: {ocupados_semana}")
                    print(f"Turnos ocupados del dia lunes: {ocupados_lunes} ")
                    print(f"Turnos ocupados de dia martes: {ocupados_martes} ")

                    if lunes_1 == "":
                        libres_lunes += 1
                    if lunes_2 == "":
                        libres_lunes += 1
                    if lunes_3 == "":
                        libres_lunes += 1
                    if lunes_4 == "":
                        libres_lunes += 1
                    
                    if martes_1 == "":
                        libres_martes += 1
                    if martes_2 == "":
                        libres_martes += 1
                    if martes_3 == "":
                        libres_martes += 1
                    if libres_lunes <= 0:
                        print("No se encuentran turnos disponibles. ")
                    else:
                        print(f"turnos libres del dia lunes: {libres_lunes} ")
                    if libres_martes <= 0:
                        print("No se encuentran turnos disponibles. ")
                    else:
                        print(f"turnos libres del dia martes: {libres_martes} ")
                    if ocupados_lunes > ocupados_martes:
                        print(f"Dia lunes tiene mas turnos ocupados con: {ocupados_lunes} turnos. ")
                    elif ocupados_lunes == ocupados_martes:
                        print("Lunes tiene los mismos turnos ocupados que el martes. ")
                    else:
                        print(f"Martes tiene mas dias ocupados con: {ocupados_martes} turnos. ")
                case _:
                    print("sistema cerrado correctamente. ")
                    break
        else:
            print("opcion invalida, elija entre el 1 y 5. ")
    else:
        print("por favor ingrese un digito valido. ")      
#ejercicio 4
energia = 100 
tiempo = 12 
cerraduras_abiertas = 0 
alarma = False 
codigo_parcial = ""
forzado_exitoso = 0
continuar_nombre = True
while continuar_nombre:
    nombre = input("ingrese su nombre agente: ")
    if nombre.replace(" ","").isalpha():
        print(f"bienvenido al hackeo de la boveda {nombre}! ")
        continuar_nombre = False
    else:
        print("se permiten solo letras. ")
inicio_boveda = True
while inicio_boveda:
    print("-----INICIO DE BOVEDA-----")
    print("---SUGERENCIA---si decides forzar 3 veces seguidas se activa la alarma! ")
    print(f"Energia: {energia}, tiempo: {tiempo} ")
    print("1---FORZAR CERRADURA (costo: -20 energía, -2 tiempo) ")
    print("2---HACKEAR PANEL (costo: -10 energía, -3 tiempo) ")
    print("3---DESCANSAR (costo: +15 energía (máx 100), -1 tiempo; si alarma ON: -10 energia extra) ")
    print("4---SALIR--- ")
    decision = input("Elija lo que quiera hacer (1-5): ")
    if decision.isdigit():
        decision = int(decision)
        if decision in (1,2,3,4,5):
            match decision:
                case 1:
                        continuar_forzar = True
                        if energia > 0 or tiempo > 0 or cerraduras_abiertas < 3:
                            while continuar_forzar:
                                    energia -= 20
                                    tiempo -= 2
                                    cerraduras_abiertas += 1
                                    forzado_exitoso += 1
                                    print(f"forzado exitoso {forzado_exitoso} ")
                                    print(f"energia restante {energia}, tiempo restante {tiempo} ")
                                    continuar_forzar = False
                                    if energia <= 40:
                                        print("HAY RIESGO DE ALARMA ")
                                        des_alarma = input("elija un 1-3, uno de los tres numeros activa la alarma...:")
                                        if des_alarma.isdigit():
                                            des_alarma = int(des_alarma)
                                            if des_alarma == 3:
                                             print("LA ALARMA SE ACTIVO. ¡GAME OVER!")
                                             alarma = True
                                             inicio_boveda = False
                                            elif des_alarma in (1,2):
                                                print("la alarma sigue desactivada, continue. ")
                                                continuar_forzar = False   
                                        else:
                                            print("solo puede ingresar digitos del 1-3. ")
                                        
                        else:
                            print("La boveda se bloqueo por mala practica, ¡ESTAS ACABADO! ")
                            inicio_boveda = False
                case 2:
                    energia -= 10
                    tiempo -= 3
                    for hack in range(1,5):
                        codigo_parcial += "A"
                        print(f"progreso {codigo_parcial}, a las 8 letras se desbloquea 1 cerradura. ")
                        print(f"energia restante ({energia}) ")
                        print(f"tiempo restante ({tiempo}) ")
                    if len(codigo_parcial) >= 8 and cerraduras_abiertas < 3:
                        print(f"se abrió otra cerradura correctamente! ")
                        cerraduras_abiertas +=1
                        codigo_parcial = ""
                    if cerraduras_abiertas >= 3:
                        print("la boveda tiene 3 cerraduras abiertas,¡USTED HA GANADO!")
                        print("FELICITACIONES! ")
                        inicio_boveda = False
                    if tiempo <= 0:
                        print("¡LA ALARMA SE HA ACTIVADO, SE HA QUEDADO SIN TIEMPO!")
                        print("---GAME OVER---")
                        alarma = True
                        inicio_boveda = False

                case 3:
                    if energia < 100 and tiempo < 12:
                        energia += 15
                        tiempo += 1
                        print (f"energia: {energia}, tiempo: {tiempo}")
                case _:
                    print("SALIO CORRECTAMENTE ")
                    inicio_boveda = False
        else:
            print("por favor ingrese algun digito disponible del menu. ")
    else:
        print("solo puede ingresar digitos. ")
#ejercicio 5
print("-----BIENVENIDO A LA ARENA DEL GLADIADOR-----")
continuar_inicio = True
while continuar_inicio:
    nombre_gladiador = input("Ingrese el nombre del gladiador: ").upper()
    if nombre_gladiador.replace(" ","").isalpha():
        print(f"¡{nombre_gladiador}! PREPARATE PARA COMBATIR. ")
        continuar_inicio = False
    else:
        print("solo se permiten letras para el nombre del gladiador. ")
Vida_del_Gladiador = 100 #(int)  
Vida_del_Enemigo = 100 #(int)  
pociones_De_vida = 3
daño_base  = 15
daño_base_enemigo = 12
turno_gladiador = True

if Vida_del_Enemigo > 0 and Vida_del_Gladiador > 0:
    continuar_menu = True
    while continuar_menu:
        print(f"vida del gladiador:HP {Vida_del_Gladiador}. ")
        print(f"vida del enemigo:HP {Vida_del_Enemigo}. ")
        print(f"pociones de vida {pociones_De_vida}. ")
        print("----INICIO----")
        print("1---ATAQUE PESADO---(15 de daño) ")
        print("2---RAFAGA VELOZ---(15 de daño) ")
        print("3---CURACION--- ")
        decision = input("Ingrese su accion: (1-3) ")
        if decision.replace(" ","").isdigit():
            decision = int(decision)
            if decision >= 1 and decision <= 3:
                    match decision:
                        case 1:
                            print("¡INICIA UN ATAQUE PESADO!")
                            Vida_del_Enemigo -= 15
                            if Vida_del_Enemigo < 20:
                                print("¡GOLPE CRITICO! ")
                                Vida_del_Enemigo -= (15*1.5)
                                print(f"Atacaste al enemigo por {15*1.5} puntos de daño")
                                print(f"¡ENEMIGO DERROTADO! ")
                                continuar_menu = False
                            else:
                                print(f"Atacaste al enemigo por 15 puntos de daño")
                                print(f"vida del enemigo: {Vida_del_Enemigo}. ")
                                print("TURNO DEL CONTRINCANTE. ")
                                print("Realiza un ataque de 12 puntos de vida. ")
                                Vida_del_Gladiador -= 12
                                if Vida_del_Gladiador <= 0:
                                    print(f"{nombre_gladiador} HA SIDO DERROTADO EN BATALLA. ¡HAS PERDIDO!")
                                    continuar_menu = False
                        case 2:
                            print("INICIO DE GOLPES RAPIDOS ")
                            for golpe in range(1,4):
                                Vida_del_Enemigo -= 5
                                print("Golpe conectado por 5 de daño")
                            print("¡EL ENEMIGO CONTRAATACA POR 12 PUNTOS DE DAÑO! ")
                            Vida_del_Gladiador -= 12
                            if Vida_del_Gladiador <= 0:
                                    print(f"{nombre_gladiador} HA SIDO DERROTADO EN BATALLA. ¡HAS PERDIDO!")
                                    continuar_menu = False
                                
                        case 3:
                            if pociones_De_vida > 0:
                                print("Gladiador fue curado con una pocion de vida, +30 HP ")
                                pociones_De_vida -= 1
                                Vida_del_Gladiador += 30
                                print("¡El enemigo ha atacado! por 12 puntos de daño..")
                                Vida_del_Gladiador -= 12   
                            else:
                                print("¡NO QUEDAN POCIONES DISPONIBLES! SE SALTA EL TURNO.")
                                print("¡EL ENEMIGO DECIDIO ATACAR! ")
                                Vida_del_Gladiador -= 12
                                if Vida_del_Gladiador <= 0:
                                    print(f"{nombre_gladiador} HA SIDO DERROTADO EN BATALLA. ¡HAS PERDIDO!")
                                    continuar_menu = False
    
            else:
                print("Solo puede ingresar un digito del 1 al 3. ")
        else:
            print("Solo puede ingresar digitos. ")
        if Vida_del_Gladiador <= 0:
                print("¡EL ENEMIGO HA DERROTADO AL GLADIADOR!HAS PERDIDO.")
                continuar_menu = False
        else: 
            if Vida_del_Enemigo <= 0:
                print(f"¡{nombre_gladiador} HA DERROTADO AL ENEMIGO! HAS GANADO.")