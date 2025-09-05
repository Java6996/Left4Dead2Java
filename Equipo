package tp_final_poo;
import javax.swing.JOptionPane;
import java.util.ArrayList;

import java.util.List;
public class Equipo {//Clase que gestiona la campaña y organiza los enfrentamientos por capitulos.
	private GestorEquipos gestorJugador; //Variable para acceder a la lista de jugadores cargados previamente.

    public Equipo(GestorEquipos gestorJugador) { //Constructor que recibe el gestor de jugadores.

        this.gestorJugador = gestorJugador;
    }
    
    public void empezar(int numeroCapitulos) { //Metodo para iniciar la partida con la cantidad de capitulos ingresada.

        if (numeroCapitulos <1 || numeroCapitulos>5) {//Verificar que el numero de capitulos esté entre 1 y 5.
            JOptionPane.showMessageDialog(null, "Error: el número de capítulos debe ser entre 1 y 5.");
            return;
        }
        if (gestorJugador.getListaJugadores().size() >= 8 && gestorJugador.getListaJugadores().size() <= 8) {//Verificar que haya 8 jugadores.
            //Obtener los 8 jugadores.
        	Jugadores jugador1 = gestorJugador.getListaJugadores().get(0); //Jugador zombi
            Jugadores jugador2 = gestorJugador.getListaJugadores().get(1); //Jugador zombi
            Jugadores jugador3 = gestorJugador.getListaJugadores().get(2); //Jugador zombi
            Jugadores jugador4 = gestorJugador.getListaJugadores().get(3); //Jugador zombi
            Jugadores jugador5 = gestorJugador.getListaJugadores().get(4); //Jugador superviviente
            Jugadores jugador6 = gestorJugador.getListaJugadores().get(5); //Jugador superviviente
            Jugadores jugador7 = gestorJugador.getListaJugadores().get(6); //Jugador superviviente
            Jugadores jugador8 = gestorJugador.getListaJugadores().get(7); //Jugador superviviente
            for (int i = 1; i <= numeroCapitulos; i++) { //Por cada capitulo, se crean los enfrentamientos y se juegan las rondas.
                List<Jugadores[]> enfrentamiento = new ArrayList<>(); //Lista de pares de jugadores para este capitulo.
                //Agregar 4 enfrentamientos por capítulo.
                //Los pares estan fijos desde que agregas a los jugadores desde el menu principal, por tanto, estos no estan formados de manera aleatorio.
                enfrentamiento.add(new Jugadores[]{jugador1, jugador3}); //SUPERVIVIENTE1 vs ZOMBIE1
                enfrentamiento.add(new Jugadores[]{jugador2, jugador4}); //SUPERVIVIENTE2 vs ZOMBIE2
                enfrentamiento.add(new Jugadores[]{jugador6, jugador5}); //SUPERVIVIENTE3 vs ZOMBIE3
                enfrentamiento.add(new Jugadores[]{jugador8, jugador7}); //SUPERVIVIENTE4 vs ZOMBIE4
                Capitulos capitulo = new Capitulos(i, enfrentamiento); //Crear un nuevo capítulo con los enfrentamientos.
                //Ejecutar los enfrentamientos normales (supervivientes y zombies) e inversas (zombies [supervivientes] y supervivientes [zombies]) del capítulo.
                capitulo.jugarRonda(); //Primera ronda.
                capitulo.jugarRondaInversa(); //Intercambiar los roles.
                capitulo.mostrarResultados(); //Mostrar los resultados.
	        }

        } else {
        	//En caso de que no haya jugadores en las listas.
            JOptionPane.showMessageDialog(null, "Error: no hay suficientes jugadores en la lista.");
        }
        //Mensaje de enfrentamiento finalizado.
        JOptionPane.showMessageDialog(null, "Fin de la campaña.");
        gestorJugador.mostrarJugadores(); //Mostrar los puntos de los jugadores.
        //Variables para acumular los puntos para ambos equipos.
        int puntosZombie = 0;
        int puntosSuperviviente = 0;
        //Mostrar los puntos por cada jugador.
        for (Jugadores jugador : gestorJugador.getListaJugadores()) {
            JOptionPane.showMessageDialog(null, jugador.getNombre() + " - Puntos: " + jugador.getPuntos());
        }
        //Sumar puntos según el rol que ocuparon en los enfrentamientos.
        List<Jugadores> jugadores = gestorJugador.getListaJugadores();
        for (int i = 0; i < jugadores.size(); i++) {
            Jugadores jugador = jugadores.get(i);

            if (i < jugadores.size() / 2) {
                puntosZombie += jugador.getPuntos();
            } else {
                puntosSuperviviente += jugador.getPuntos();
            }
        }
        //Mostrar los resultados.
        if (puntosZombie > puntosSuperviviente) {
        	JOptionPane.showMessageDialog(null, "¡Ganaron los Zombies!");
        } else if (puntosSuperviviente > puntosZombie) {
        	JOptionPane.showMessageDialog(null, "¡Ganaron los Supervivientes!");
        } else {
        	JOptionPane.showMessageDialog(null, "¡Empate!");
        }
        //Mostrar los puntos de cada equipo.
        JOptionPane.showMessageDialog(null, "Puntos totales: " + "\nEquipo Zombie: " + puntosZombie + "\nEquipo Superviviente: " + puntosSuperviviente);
    }
}
