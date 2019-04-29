import java.io.FileWriter;
import java.io.IOException;
import java.text.DecimalFormat;
import java.util.Scanner;

/**
 * 
 */

/**
 * @author quillan.ogle
 *
 */
public class Main {
	public static void main(String args[]) {
		//math class
		calculations calc = new calculations();
		
		//setup user input
		Scanner kbd = new Scanner(System.in);
		double ann;
		double sal;
		double rate;
		
		//get fixed salary just in case it changes
		System.out.print("Enter fixed sallary: $");
		sal = kbd.nextDouble();
		
		//get annual sales for calculation
		System.out.print("Enter annual sales: $");
		ann = kbd.nextDouble();
		
		//get commission percentage
		System.out.print("Enter commission percentage: " + "%");
		rate = kbd.nextDouble();
		rate /= 100;
		
		//calculate total annual compensation
		double comp = calc.calculate(sal, ann, rate);
		
		//format
		DecimalFormat formatter = new DecimalFormat("#,###.00");
		
		//Print out compensation
		System.out.printf("The total annual compensations is $" + formatter.format(comp));
		
		//Write to file
		try {
			FileWriter fileWriter = new FileWriter("C:\\Users\\quillan.ogle\\eclipse-workspace\\Week 3 Control Structures\\src\\compensation.txt");
			fileWriter.write("Salary: $" + formatter.format(sal) + "\nAnnual Sales: $" + formatter.format(ann) + "\nCommission Rate: " + 
			rate + "\nAnnual Compensation: $" + formatter.format(comp));
			fileWriter.close();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
		

	}

}
