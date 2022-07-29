import java.util.*;
class project{
	public static void main(String args[]){
		Scanner input=new Scanner(System.in);
		
		String sId [] = new String [100]; 
		String sName [] = new String [100]; 
		int prfMarks [] = new int [100]; 
		int dbmsMarks [] = new int [100]; 
		int total[] = new int[100];
		double avarage[]=new double[100];
		double ran[]=new double[avarage.length];
		
		
		
		
		
		
		optionList();
		int option=selection();
		int count=0;
		
		switch(option){
			case 1 :clearConsole();
					addNewStudent();
					String ask;
					int count1=count;
				do{ 
					System.out.println(" ");
					String d1=getId();
					sId[count1]=d1;
					String d2=getName();
					sName[count1]=d2;
					count1++;
					System.out.println(" ");
					System.out.print("Student has been Added Successfully..");
					System.out.print("Do you want to Add a new Student (y/n) : ");
					ask=input.next();
					}while(ask.equals("y"));
					clearConsole();
					optionList();
					selection();
					count=count1;
				
			case 2 :clearConsole();
					addNewStudentWithMarks();
					String ask2;
					int count2=count;
				do{
					System.out.println(" ");
					String d3=getId();
					sId[count2]=d3;
					String d4=getName();
					sName[count2]=d4;
					System.out.println(" ");
					int d5=getPrfMarks();
					prfMarks[count2]=d5;
					int d6=getDbmsMarks();
					dbmsMarks[count2]=d6;
					int tot=prfMarks[count2]+dbmsMarks[count2];
					total[count2]=tot;
					double av=(double)tot/2;
					avarage[count2]=av;
					ran[count2]=avarage[count2]; 
					for(int i=avarage.length-1;i>0; i--){	
					for(int j=0; j<i; j++){				
					if(avarage[j]<avarage[j+1]){		
					double t=avarage[j];		
					avarage[j]=avarage[j+1];	
					avarage[j+1]=t;		
					}		
					}		
					}		
					System.out.println(" ");
					System.out.print("Student has been Added Successfully..");
					count2++;
					System.out.print(" Do you want to Add a new Student (y/n) : ");
					ask2=input.next();
					}while(ask2.equals("y"));
					clearConsole();
					
					System.out.println("");
					optionList();
					selection();
					
		case 3 :clearConsole();
					addMarks();
					System.out.println(" ");
					String ask3;
					do{
					System.out.print("Enter Student Id : ");
					String checkId=input.next();
					for(int i=0;i<200;i++){
					if(checkId.equals(sId[i])){
					   System.out.println("Student Name : "+sName[i]);
					   System.out.println(" ");
						int d7=getPrfMarks();
						prfMarks[i]=d7;
						int d8=getDbmsMarks();
						dbmsMarks[i]=d8;
						int tot=prfMarks[i]+dbmsMarks[i];
						total[i]=tot;
						double av=(double)tot/2;
						avarage[i]=av;
						ran[i]=avarage[i]; 
					for(int p=avarage.length-1;p>0; p--){	
					for(int j=0; j<p; j++){				
					if(avarage[j]<avarage[j+1]){		
					double t=avarage[j];		
					avarage[j]=avarage[j+1];	
					avarage[j+1]=t;		
					}		
					}		
					}
						System.out.println(" ");
						System.out.print("Marks have been Added successfully..");
						System.out.println(" ");
					    break;
					}else{
						continue;
						}
					} 
						System.out.println(" ");
						System.out.print("Do you want Search Student Again ? (y/n) : ");
						ask3=input.next();
					}while("y".equals(ask3));
					clearConsole();
					optionList();
					selection();
					
			   case 4 :clearConsole();
					updateStudentDetail();
					System.out.println(" ");
					String ask4;
					do{
						System.out.println(" ");
						System.out.print("Enter Student Id : ");
						String checkId2=input.next();
						for(int i=0;i<200;i++){
							if(checkId2.equals(sId[i])){
								System.out.println("Student Name : "+sName[i]);
								System.out.println(" ");
								System.out.print("Enter new Name : ");
								sName[i] =input.next();
								System.out.println("Update Successfully..");
								break;
								}
								}
						System.out.print("Do you want Update Again ?(y/n) : ");
						ask4=input.next();
						}while("y".equals(ask4));
						clearConsole();
						optionList();
						selection();

				 case 5 :clearConsole();
						updateMarks();
						System.out.println(" ");
						String ask5;
						do{
							System.out.println(" ");
							System.out.print("Enter Student Id : ");
							String checkId3=input.next();
							for(int i=0;i<200;i++){
								if(checkId3.equals(sId[i])){
									System.out.println("Student Name : "+sName[i]);
									System.out.println(" ");
									System.out.println("Programming Fundamentals Marks : "+prfMarks[i]);
									System.out.println("Database Management Systems Marks : "+dbmsMarks[i]);
									System.out.println(" ");
									int d9=getPrfMarks();
									prfMarks[i]=d9;
									int d10=getDbmsMarks();
									dbmsMarks[i]=d10;
									int tot=prfMarks[i]+dbmsMarks[i];
									total[i]=tot;
									double av=(double)tot/2;
									avarage[i]=av;
									ran[i]=avarage[i]; 
									for(int q=avarage.length-1;q>0; q--){	
									for(int j=0; j<q; j++){				
									if(avarage[j]<avarage[j+1]){		
									double t=avarage[j];		
									avarage[j]=avarage[j+1];	
									avarage[j+1]=t;		
									}		
									}		
									}		
									System.out.println(" ");
									System.out.print("Marks have been Update Successfully..");
									System.out.println(" ");
									break;
									}
								    }
							System.out.println(" ");
							System.out.print("Do you want Update Again ?(y/n) : ");
						    ask5=input.next();
							}while("y".equals(ask5));
							clearConsole();
							optionList();
							selection();
							
				 case 6 : clearConsole();
						 deleteStudents();
						 System.out.println(" ");
						 String ask6;
						 do{
							 System.out.println(" ");
							 System.out.print("Enter Student Id : ");
							 String checkId4=input.next();
							 for(int i=0;i<200;i++){
								 if(checkId4.equals(sId[i])){
									 System.out.println(" ");
									 sId[i] ="null";
									 sName[i] ="null";
									 prfMarks[i] =0;
									 dbmsMarks[i] =0;
									 System.out.println("Delete successfully..");
									 System.out.println(" ");
									 break;
									 }
									 } 
							 System.out.println(" ");
							 System.out.print("Do you want Delete another Student ?(y/n) : ");
						     ask6=input.next();
							 }while("y".equals(ask6));
							 clearConsole();
							 optionList();
							 selection();
							 
				case 7 : clearConsole();
						 printStudentDetails();
						 System.out.println(" ");
						 String ask7;
						 do{ 
							 System.out.println(" ");
							 int get;
							 System.out.print("Enter Student Id : ");
							 String checkId5=input.next();
							
							for(int i=0;i<avarage.length;){
								  if(checkId5.equals(sId[i])){
									  System.out.println("Student Name : "+sName[i]);
									  System.out.println(" ");
									  get=i+1;
								
								for(int k=0;k<avarage.length;){
								if(avarage[get]!= ran[k]){
								k++;
								continue;
								}else{
								int x=k;
							tableLine();
							System.out.println("| Programming Fundamentals Marks	  | "+prfMarks[i]+" 	 |");
							System.out.println("| Database Management Systems Marks 	  | "+dbmsMarks[i]+"	 |");
							System.out.println("| Total Marks	 			  | "+(prfMarks[i]+dbmsMarks[i])+"	 |");
							System.out.println("| Avg. Marks 			  	  | "+(prfMarks[i]+dbmsMarks[i])/2+"   |");
							System.out.println("| Rank 					  | "+x+"    |");
							tableLine();
							System.out.println(" ");
							break;
								}
								}
								}
						i++;
						 }//for
							 System.out.print("Do you want to Search another Student Details?(y/n) : ");
						     ask7=input.next();
							 }while("y".equals(ask7));
							 clearConsole();
							 optionList();
							 selection();
							 
					case 8 : clearConsole();
							 printStudentRank();
							 System.out.println("");
							
							 String ask8;
					 System.out.println();
					 do{ 
						System.out.println("+------+-------------+------------+----------------+------------------+");
						System.out.print("|Rank  |");
						System.out.print(" Id          |");
						System.out.print(" Name       |");
						System.out.print(" Total Marks    |");
						System.out.println(" Avg.  Marks      |");
						System.out.println("+------+-------------+------------+----------------+------------------+");
					 
						for(int i=0; i<9; i++){
							System.out.print("|   0" +(i+1)+" |");
							System.out.print("      "+sId[i]+"   |");
							System.out.print("       "+sName[i]+" |");
							System.out.print("              "+total[i]+" |");
							System.out.print("              "+avarage[i]+" |");
							System.out.println();
						}
						System.out.println("+------+-------------+------------+----------------+------------------+");
						System.out.println();
						System.out.print("Do you want to go back to main menu? (y/n) : ");
						ask8=input.next();
						if (ask8.equals("y")){
							clearConsole();
							optionList();
							selection();
						}else{
							break;
						}
				 }while(ask8.equals("n"));
				 clearConsole();
				 optionList();
				 selection();
				 
		case 9 : clearConsole();
				 bestInPRF();
				 String ask9;
				 System.out.println();
					 do{ 
						System.out.println("+-----+-----------+--------------+----------------+");
						System.out.print("|ID   |");
						System.out.print(" Name      |");
						System.out.print(" PRF Marks    |");
						System.out.println(" DBMS  Marks    |");
						System.out.println("+-----+-----------+--------------+----------------+");
					 
						for(int i=0; i<9; i++){
							System.out.print("|"+sId[i]+" |");
							System.out.print("      "+sName[i]+" |");
							System.out.print("            "+prfMarks[i]+" |");
							System.out.print("              "+dbmsMarks[i]+" |");
							System.out.println();
						}
						System.out.println("+-----+-----------+--------------+----------------+");
						System.out.println();
						System.out.print("Do you want to go back to main menu? (y/n) : ");
						ask9=input.next();
						if (ask9.equals("y")){
							clearConsole();
							optionList();
							selection();                                                 
						}else{
							break;
						}
					}while(ask9.equals("n"));
					
			case 10 : clearConsole();
					  bestInDBMS();
					 String ask10;
					 System.out.println();
					 
					 do{ 
						System.out.println("+-----+-----------+--------------+----------------+");
						System.out.print("|ID   |");
						System.out.print(" Name      |");
						System.out.print(" PRF Marks    |");
						System.out.println(" DBMS  Marks    |");
						System.out.println("+-----+-----------+--------------+----------------+");
					 
						for(int i=0; i<9; i++){
							System.out.print("|"+sId[i]+" |");
							System.out.print("      "+sName[i]+" |");
							System.out.print("            "+prfMarks[i]+" |");
							System.out.print("              "+dbmsMarks[i]+" |");
							System.out.println();
						}
						System.out.println("+-----+-----------+--------------+----------------+");
						System.out.println();
						System.out.print("Do you want to go back to main menu? (y/n) : ");
						ask10=input.next();
						if (ask10.equals("y")){
							clearConsole();
							optionList();
							selection();                                                 
						}else{
							break;
						}
					}while(ask10.equals("n"));
	default : System.out.println("Invalid Input ..");
	
			}// close switch
		
		}// close main method
		
			
	public static void optionList(){
		System.out.println("--------------------------------------------------------------------------------------------------------------");
		System.out.println("|                                   WELCOME TO GDSE MARKS MANAGEMENT SYSTEM                                  |");
		System.out.println("--------------------------------------------------------------------------------------------------------------");
		System.out.println(" ");
		System.out.println("   [ 1 ]   Add New Student                                 [ 2 ]   Add New Student With Marks");
		System.out.println("   [ 3 ]   Add Marks                                       [ 4 ]   Update Student Details ");
		System.out.println("   [ 5 ]   Update Marks                                    [ 6 ]   Delete Student ");
		System.out.println("   [ 7 ]   Print Student Details                           [ 8 ]   Print Student Marks ");
		System.out.println("   [ 9 ]   Best In Programming Fundamentals                [ 10 ]  Best In Database Management System ");
		System.out.println(" ");
		
		 }
	
	public static void addNewStudent(){
		clearConsole();
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                                          ADD NEW STUDENT                                |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("  ");
		System.out.println("  ");
			
			}
			
			
			public static void addNewStudentWithMarks(){
		System.out.println(" ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                                ADD NEW STUDENT  WITH MARKS                               |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
				}
				
				
				public static void addMarks(){
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                          	       ADD MARKS                                          |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					}
					
				public static void updateStudentDetail(){
		System.out.println(" ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                             	  UPDATE STUDENT DETAILS                                  |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					
					}
					
					public static void updateMarks(){
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                          	    UPDATE MARKS                                          |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					}
					
					public static void deleteStudents(){
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                          	      DELETE STUDENT                                      |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					}
				
				public static void printStudentDetails(){
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                          	    PRINT STUDENT DETAILS                                 |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					}
					
					public static void printStudentRank(){
		System.out.println("  ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                          	     PRINT STUDENT RANK                                   |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					}
					
					public static void bestInPRF(){
		System.out.println(" ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                                BEST IN PROGRAMMING FUNDAMENTALS                         |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
	}
		
		public static void bestInDBMS(){
		System.out.println(" ");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println("|                              BEST IN DATABASE MANAGEMENT SYSTEM                         |");
		System.out.println(" ------------------------------------------------------------------------------------------ ");
		System.out.println(" ");
					
					}
					
				public static void tableLine(){
		System.out.println("+-----------------------------------------+------+");
					}
					
	
	public static int selection(){
	Scanner input=new Scanner(System.in);
		System.out.println(" ");
		System.out.print("Enter an Option to continue > ");
		int option=input.nextInt();
		return option;
		}
	
	
	
	
	
	
	
		public static String getId(){
				Scanner input=new Scanner(System.in);
				System.out.print("Enter Student Id : ");
				String sId =input.next();
				return sId;
			}
			
				public static String getName(){
					Scanner input=new Scanner(System.in);				
					System.out.print("Enter Student Name : ");
					String sName =input.next();
					return sName;
				}
				
				public static int getPrfMarks(){
					Scanner input=new Scanner(System.in);
					int pMarks;
					do{
					System.out.print("Programming Fundamentals Marks : ");
					pMarks=input.nextInt();
					while(pMarks>100 || pMarks<0){
					System.out.println("Invalid Marks, Please Enter correct Marks. ");	
					System.out.print("Programming Fundamentals Marks : ");
					pMarks=input.nextInt();
					}
					}while(pMarks<0 && pMarks>100);	
					return pMarks;
			   }// close method
			   
			   public static int getDbmsMarks(){
					Scanner input=new Scanner(System.in);
					int dMarks;
					do{
					System.out.print("Database Management System Marks : ");
					dMarks=input.nextInt();
					while(dMarks>100 || dMarks<0){
					System.out.println("Invalid Marks, Please Enter correct Marks. ");	
					System.out.print("Database Management System Marks : ");
					dMarks=input.nextInt();	
					}
					}while(dMarks<0 && dMarks>100);
					return dMarks;
			   }//close method
	
	
	
	
	
	
	
	
		public final static void clearConsole() {  
			try { 
			final String os = System.getProperty("os.name");  
			if (os.contains("Windows")) { 
			new ProcessBuilder("cmd", "/c", "cls").inheritIO().start().waitFor(); 
		} else { 
			System.out.print("\033[H\033[2J");  
			System.out.flush(); 
		} 
		} catch (final Exception e) { 
			e.printStackTrace(); 

		}
	}
	
	
	
	
	
	
	} // End Class
