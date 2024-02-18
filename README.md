# This code was created as an assignment for ICS4UA: AP Computer Science.
## Language: Java
#### Item, price, maximum stock, quantity, and other variables can be edited.
```java
package vendingsystem;

import java.util.Scanner;

public class Selection {
	
	/*
	 * 
	 * CONSTRUCTORS
	 * 
	 */
	
	public class Stock {
		
		String productName;
		double productPrice;
		int productStock;
		int maxStock;
		int productSold;
		
		public Stock(String productName, double productPrice, int productStock, int maxStock, int productSold) {
			this.productName = productName;
			this.productPrice = productPrice;
			this.productStock = productStock;
			this.maxStock = maxStock;
			this.productSold = productSold;
			}
		/*
		 * 
		 * METHODS
		 * 
		 */
		public void getPrice() {
			System.out.println(productPrice);
		}
		
		public void setPrice(double newPrice) {
			this.productPrice = newPrice;
		}
		
		public void currentStock() {
			System.out.println(productStock + "/10");
		}
		
		public void totalSales(double totalSales) {
			totalSales = productSold * productPrice;
		}
		
		public void vendingDisplay () { 
			System.out.println(productName + " (" + productStock + "/10)" + " ($" + productPrice + ")");
		}
		
	}

	public static void main(String[] args) {
		
		/*
		 * 
		 * INITIALIZATION
		 * 
		 */
		Selection selection = new Selection();
		Stock SPK = selection.new Stock ("Sour Patch Kids", 5.0, 10, 10, 0);
		Stock MARS = selection.new Stock ("Mars", 3.5, 10, 10, 0);
		Stock GUM = selection.new Stock ("Gum", 2.5, 10, 10, 0);
		Stock TKS = selection.new Stock ("Takis", 4.5, 10, 10, 0);
		Stock PEP = selection.new Stock ("Pepsi", 3.0, 10, 10, 0);
		int currentStock = 50; // Stock of items left
		boolean verificationSystem; // Used to confirm whether or not user input is correct.
		boolean restart = true;
		double moneySpent = 0;
		double moneyWallet = 100;
		double revenue = 0; // Revenue made off of vending machine!
		Scanner scanner = new Scanner(System.in);
				
		// Starting message.
		while (restart = true) {
        System.out.println("____________________________");
        System.out.println("|  __   __   __   __   __  |");
        System.out.println("| |  | |  | |  | |  | |	 | |");
        System.out.println("| | 1| | 2| | 3| | 4| |	5| |");
        System.out.println("| |__| |__| |__| |__| |__| |");
        System.out.println("|__________________________|");
        System.out.println("|                      	   |");
        System.out.println("|   [ VENDING MACHINE ]    |");
        System.out.println("|__________________________|");
        System.out.println("\nWelcome to the Vending Machine! Here are your options!");
        SPK.vendingDisplay();
        MARS.vendingDisplay();
        GUM.vendingDisplay();
        TKS.vendingDisplay();
        PEP.vendingDisplay();
				
		/*			
		 * 
		 * DETECTION 
		 * 
		 */
		
		String userChoice = scanner.nextLine();
		
		// Detects whether or not the system has enough stock for the specified item.
		if (userChoice.equals("Sour Patch Kids") && SPK.productStock <= 0) {
			System.out.println("Unfortunately, this item is out of stock. Please pick another item.");
		}
		if (userChoice.equals("Mars") && MARS.productStock <= 0) {
			System.out.println("Unfortunately, this item is out of stock. Please pick another item.");
		}
		if (userChoice.equals("Gum") && GUM.productStock <= 0) {
			System.out.println("Unfortunately, this item is out of stock. Please pick another item.");
		}
		if (userChoice.equals("Takis") && TKS.productStock <= 0) {
			System.out.println("Unfortunately, this item is out of stock. Please pick another item.");
		}
		if (userChoice.equals("Pepsi") && PEP.productStock <= 0) {
			System.out.println("Unfortunately, this item is out of stock. Please pick another item.");
		}
		
		// Detects whether or not the entered value matches the available stock in the machine.
		if (userChoice.equals("Sour Patch Kids") || userChoice.equals("Mars") || userChoice.equals("Gum") || userChoice.equals("Takis") || userChoice.equals("Pepsi")) {
			verificationSystem = true;
		}
			// Runs if the input is not a valid item in the vending machine.
		if (verificationSystem = false) {
			System.out.println("Unfortunately, you have not entered an item sold at this vending machine! Please try again.");
		}
		
		/*
		 * 
		 * CONFIRMATION
		 * 
		 */
		
		// To confirm the user input and run variable deductions (money and stock) 
			// SOUR PATCH KIDS
		if (userChoice.equals("Sour Patch Kids")) {
			System.out.println("You have selected Sour Patch Kids!\n\nPRICE: $" + SPK.productPrice + "\n\nPlease type 'CONFIRM' to purchase this item.\nYou currently have $" + moneyWallet);
			moneySpent = moneySpent + SPK.productPrice;
			SPK.productStock = SPK.productStock - 1;
			// MARS
		} else if (userChoice.equals("Mars")) {
			System.out.println("You have selected Mars!\n\nPRICE: $" + MARS.productPrice + "\n\nPlease type 'CONFIRM' to purchase this item.\nYou currently have $" + moneyWallet);
			moneySpent = moneySpent + MARS.productPrice;
			MARS.productStock = MARS.productStock - 1;
			// GUM
		} else if (userChoice.equals("Gum")) {
			System.out.println("You have selected Gum!\n\nPRICE: $" + GUM.productPrice + "\n\nPlease type 'CONFIRM' to purchase this item.\nYou currently have $" + moneyWallet);
			moneySpent = moneySpent + GUM.productPrice;
			GUM.productStock = GUM.productStock - 1;
			// TAKIS
		} else if (userChoice.equals("Takis")) {
			System.out.println("You have selected Takis!\n\nPRICE: $" + TKS.productPrice + "\n\nPlease type 'CONFIRM' to purchase this item.\nYou currently have $" + moneyWallet);
			moneySpent = moneySpent + TKS.productPrice;
			TKS.productStock = TKS.productStock - 1;
			// PEPSI
		} else if (userChoice.equals("Pepsi")) {
			System.out.println("You have selected Pepsi!\n\nPRICE: $" + PEP.productPrice + "\n\nPlease type 'CONFIRM' to purchase this item.\nYou currently have $" + moneyWallet);
			moneySpent = moneySpent + PEP.productPrice;
			PEP.productStock = PEP.productStock - 1;
		} else return;
		
		String confirmPAY = scanner.nextLine();
		currentStock = currentStock - 1;
		
		// Confirmation of payment (receipt)
		if (confirmPAY.equals("CONFIRM")) {
		moneyWallet = moneyWallet - moneySpent;
		revenue = revenue + moneySpent;
		System.out.println("\n== RECEIPT ==\n\n- ITEM: " + userChoice + "\n- PRICE: $" + moneySpent + "\n- WALLET: $" + moneyWallet + "\n\nThanks for shopping! The machine has made: $" + revenue + " :]\n\nType 'RESTART' to buy something again, or say 'DONE' to stop!");
	} else System.out.println("An error occurred with what you've typed. Please try again.");
		
		// Confirmation of continuing to use the vending machine
		String restartConfirmation = scanner.nextLine();
		if (restartConfirmation.equals("RESTART")) {
			System.out.println("\n\n\n\n\n\n");
			restart = true;
		} else if (restartConfirmation.equals("DONE")) {
			System.out.println("Thank you for shopping! Enjoy your purchase! :]");
			restart = false;
		}
		
		}
		
	}
	
}
```
