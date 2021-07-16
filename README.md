- 👋 Hi, I’m @BeginnerDevelopper
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
BeginnerDevelopper/BeginnerDevelopper is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
+import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JRadioButton;
import javax.swing.JTextField;
import javax.swing.event.ChangeEvent;
import javax.swing.event.ChangeListener;

/*
 * Permitir el ingreso de dos n�meros en controles de tipo JTextField y mediante dos controles de tipo 
JRadioButton permitir seleccionar si queremos sumarlos o restarlos. Al presionar un bot�n mostrar en un 
jlabel del JFrame el resultado de la operaci�n
 *
 *
 * 
 * */


public class Ejercicio2Swing extends JFrame implements ChangeListener, ActionListener {

		private JTextField campotxt1,campotxt2;
		private JButton calcular;
		private JRadioButton radio1, radio2;
		private JLabel numero1,numero2,resultado,cal;
	
	
		public Ejercicio2Swing() {
			
		setLayout(null);	
		//Generamos dos campos de texto el primero Suma
		campotxt1 = new JTextField("");
		campotxt1.setBounds(100, 10, 100, 30);
		add(campotxt1);
		//Campo de texto Resta
		campotxt2 = new JTextField("");
		campotxt2.setBounds(100, 50, 100, 30);
		add(campotxt2);
		
		// Creamos unos botones de chequeo para elegir sea una opcion u otra
		radio1 = new JRadioButton("Sumar");
		radio1.setBounds(100, 98, 100, 30);
		radio1.addChangeListener(this);
		add(radio1);
		
		
		radio2 = new JRadioButton("Restar");
		radio2.setBounds(100, 120, 100, 30);
		radio2.addChangeListener(this);
		add(radio2);
		
		//Calcular representa un boton de respuesta a los dos campos de texto//
		
		calcular = new JButton("Calcular");
		calcular.setBounds(100, 150, 100, 30);
		calcular.addActionListener(this);
		add(calcular);
		
		// La etiqueta JLabel mostrar� el resultado del calculo entre campotxt1 y campotxt2
		
		resultado = new JLabel("");
		resultado.setBounds(100, 180, 100, 30);
		add(resultado);
		//T�tulo del resultado de la operaci�n//
		
		cal = new JLabel("Resultado");
		cal.setBounds(10, 180, 100, 30);
		add(cal);
		//Titulo de campo de texto 1//
		numero1 = new JLabel("N�mero 1");
		numero1.setBounds(10, 10, 100, 30);
		add(numero1);
		//Titulo de campo de texto 2//
		numero2 = new JLabel("N�mero 2");
		numero2.setBounds(10, 50, 100, 30);
		add(numero2);
		
		
		
		}
	
	public static void main(String[] args) {
		
		Ejercicio2Swing ventana = new Ejercicio2Swing();	
		ventana.setBounds(0, 0, 350, 230);
		ventana.setVisible(true);
		ventana.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		ventana.setTitle("Caja de C�lculo");
	}

	@Override
	public void stateChanged(ChangeEvent e) {
		
		String cal = "";
		
		if(radio1.isSelected()) {
			
			cal = cal + "Sumar";
			
		}
		
		if(radio2.isSelected()) {
			
			cal = cal + "Restar";
			
		}
		
		
	}

	@Override
	public void actionPerformed(ActionEvent e) {
		
		//Creamos las variables boton con las cuales sumar o restar dos numeros
        //Posteriormente mostramos el resultado en una etiqueta	
		
	
		
		if(e.getSource()==calcular) {
			
			int x1,x2,total;
			
			 x1 = Integer.parseInt(campotxt1.getText());
			 x2 = Integer.parseInt(campotxt2.getText());
			
			 
			if(radio1.isSelected()) {
				
			 total = x1 + x2;
			 
			 resultado.setText(String.valueOf(total));	
			} else if (radio2.isSelected()) {
				
				
			  total = x1 - x2;
			   
			  resultado.setText(String.valueOf(total));
			}
				
		
		}
		    
		}
		
		
		
		
	}
