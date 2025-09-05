package tp_final_poo;

//Clase que representa a un jugador (ya sea zombie o superviviente).
public class Jugadores {
	    private String nombre; //Nombre del jugador.
	    private int salud; //Salud del jugador.
	    private int puntos; //Puntos acumulados.
	    
	    //Constructor que recibe nombre, salud y empezar por 0 puntos de un jugador.
	    public Jugadores(String nombre, int salud) {
	        this.nombre = nombre;
	        this.salud = salud;
	        this.puntos = 0;
	    }

	    public String getNombre() { //Devolver el nombre del jugador.
	        return nombre;
	    }

	    public int getSalud() { //Devolver salud del jugador.
	        return salud;
	    }

	    public void recibirdaño(int daño) { //Restar salud, es decir, aplicando daño al jugador.
	        salud -= daño;
	        if (salud < 0) {
	            salud = 0; //La salud no puede ser negativa.
	        }
	    }
	    //Sumar puntos totales al jugador.
	    public void sumarPuntos(int puntosGanados) {
	        puntos += puntosGanados;
	    }
	    //Devolver la cantidad de puntos acumulados por el jugador.
	    public int getPuntos() {
	        return puntos;
	    }
	    //Devolver True si el jugador todavia tiene salud.
	    public boolean estaVivo() {
	        return salud > 0;
	    }
	    //Representación del jugador en formato texto.
	    @Override
	    public String toString() {
	        return nombre + " - Salud: " + salud + ", Puntos: " + puntos;
	    }
}
