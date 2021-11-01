# Hospital-Management-System
Main Moule:-
package hospital;

import java.util.*;
//import java.io.Exception;
import java.util.Scanner;
public class HospitalManagement {
	public static void main(String args[])
	
  {
		
      String months[] = {
          "Jan",
          "Feb",
          "Mar",
          "Apr",
          "May",
          "Jun",
          "Jul",
          "Aug",
          "Sep",
          "Oct",
          "Nov",
          "Dec"
      };
      Calendar calendar = Calendar.getInstance();
      //System.out.println("--------------------------------------------------------------------------------");
      int count1 = 4, count3 = 4, count4 = 4, count5 = 4, count6 = 0;
      System.out.println("\n--------------------------------------------------------------------------------");
      System.out.println("            *** Welcome to Hospital Management System Project in Java ***");
      System.out.println("--------------------------------------------------------------------------------");
      System.out.print("Date: " + months[calendar.get(Calendar.MONTH)] + " " + calendar.get(Calendar.DATE) + " " + calendar.get(Calendar.YEAR));
      System.out.println("\t\t\t\t\t\tTime: " + calendar.get(Calendar.HOUR) + ":" + calendar.get(Calendar.MINUTE) + ":" + calendar.get(Calendar.SECOND));
      doctor[] d = new doctor[25];
      patient[] p = new patient[100];
      lab[] l = new lab[20];
      facility[] f = new facility[20];
      medical[] m = new medical[100];
      billing[] b = new billing[100];
      int i;
      for (i = 0; i < 25; i++)
          d[i] = new doctor();
      for (i = 0; i < 100; i++)
          p[i] = new patient();
      for (i = 0; i < 20; i++)
          l[i] = new lab();
      for (i = 0; i < 20; i++)
          f[i] = new facility();
      for (i = 0; i < 100; i++)
          m[i] = new medical();
      for (i = 0; i < 100; i++)
          b[i] = new billing();

      d[0].did = "21";
      d[0].dname = "Dr.Arif Manyar";
      d[0].specilist = "ENT";
      d[0].appoint = "5-11AM";
      d[0].doc_qual = "MBBS,MD";
      d[0].droom = 17;
      d[0].consult_fee = 500;
      d[1].did = "32";
      d[1].dname = "Dr.Ritwik Singh";
      d[1].specilist = "Physician";
      d[1].appoint = "10-3AM";
      d[1].doc_qual = "MBBS,MD";
      d[1].droom = 45;
      d[1].consult_fee = 400;
      d[2].did = "17";
      d[2].dname = "Dr.Vatsal Sanghal";
      d[2].specilist = "Surgeon";
      d[2].appoint = "8-2AM";
      d[2].doc_qual = "BDM";
      d[2].droom = 8;
      d[2].consult_fee = 300;
      d[3].did = "33";
      d[3].dname = "Dr.Richa Singh";
      d[3].specilist = "Artho";
      d[3].appoint = "10-4PM";
      d[3].doc_qual = "MBBS,MS";
      d[3].droom = 40;
      d[3].consult_fee = 200;
      /*
      p[0].pid = "12";
      p[0].patname = "Pankaj Sharma";
      p[0].docname = "Pankaj Sharma";
      p[0].disease = "Cancer";
      p[0].sex = "Male";
      p[0].admit_status = "y";
      p[0].age = 30;
      p[1].pid = "13";
      p[1].patname = "Sumit Sharma";
      p[1].docname = "Pankaj Sharma";
      p[1].disease = "Cold";
      p[1].sex = "Male";
      p[1].admit_status = "y";
      p[1].age = 23;
      p[2].pid = "14";
      p[2].patname = "Alok Sharma";
      p[2].docname = "Pankaj Sharma";
      p[2].disease = "Maleriya";
      p[2].sex = "Male";
      p[2].admit_status = "y";
      p[2].age = 45;
      p[3].pid = "15";
      p[3].patname = "Ravi Sharma";
      p[3].docname = "Pankaj Sharma";
      p[3].disease = "Diabetes";
      p[3].sex = "Male";
      p[3].admit_status = "y";
      p[3].age = 25;
      */
      m[0].med_name = "Corex";
      m[0].med_comp = "Cino pvt";
      m[0].exp_date = "9-5-16";
      m[0].med_cost = 55;
      m[0].count = 8;
      m[1].med_name = "Nytra";
      m[1].med_comp = "Ace pvt";
      m[1].exp_date = "4-4-15";
      m[1].med_cost = 500;
      m[1].count = 5;
      m[2].med_name = "Brufa";
      m[2].med_comp = "Reckitt";
      m[2].exp_date = "12-7-17";
      m[2].med_cost = 50;
      m[2].count = 56;
      m[3].med_name = "Pride";
      m[3].med_comp = "DDF pvt";
      m[3].exp_date = "12-4-12";
      m[3].med_cost = 1100;
      m[3].count = 100;

      l[0].facility = "X-ray";
      l[0].lab_cost = 100;
      l[1].facility = "CT-Scan";
      l[1].lab_cost = 1200;
      l[2].facility = "OR-Scan";
      l[2].lab_cost = 500;
      l[3].facility = "Blood-Bank";
      l[3].lab_cost = 50;

      f[0].fac_name = "Ambulance";
      f[1].fac_name = "Admit Facility ";
      f[2].fac_name = "Canteen";
      f[3].fac_name = "Emergency";

      

      Scanner input = new Scanner(System.in);
      int choice, j, c1, status = 1, s1 = 1, s3 = 1, s4 = 1, s5 = 1, s6 = 1;
      while (status == 1)
      {
          System.out.println("\n                                    MAIN MENU");
          System.out.println("-----------------------------------------------------------------------------------------");
          System.out.println("1.Doctos  2. Patients  3.Medicines  4.Laboratories  5. Facilities 6. Billing 7. Exit");
          System.out.println("-----------------------------------------------------------------------------------------");
          choice = input.nextInt();
          switch (choice)
          {
              case 1:
                  {
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("                      **DOCTOR SECTION**");
                      System.out.println("--------------------------------------------------------------------------------");
                      s1 = 1;
                      while (s1 == 1)
                      {
                          System.out.println("1.Add New Entry\n2.Existing Doctors List");
                          c1 = input.nextInt();
                        //  if(c1!=1 && c1!=2)
                          //	throw new Exception("IOException: You have Entered Wrong Choice Program Terminated!");
                          switch (c1)
                          {
                              case 1:
                                  {
                                      d[count1].new_doctor();count1++;
                                      break;
                                  }
                              case 2:
                                  {
                                      System.out.println("---------------------------------------------------------------------------------------------------------------------");
                                      System.out.println(" id \t\t Name \t\t   Specilist \t Qualification \t   Timing \t   Room No. \tConsultation fee");
                                      System.out.println("---------------------------------------------------------------------------------------------------------------------");
                                      for (j = 0; j < count1; j++)
                                      {
                                          d[j].doctor_info();
                                      }
                                      break;
                                  }
                          }
                          System.out.println("\nReturn to Back Press 1 and for Main Menu Press 0");
                          s1 = input.nextInt();
                      }
                      break;
                  }
              case 2:
                  {
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("                     **PATIENT SECTION**");
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("-------------------------------------------------------------------------------------------------------------");
                      System.out.println("   id \t\t PName \t\t  DocName \t    Disease \t      Gender \t Admit Status \t      Age");
                      System.out.println("-------------------------------------------------------------------------------------------------------------");
                      for (j = 0; j < count6; j++) {
                          p[j].patient_info();
                      }                        
                      break;
                  }
              case 3:
                  {
                      s3 = 1;
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("                     **MEDICINE SECTION**");
                      System.out.println("--------------------------------------------------------------------------------");
                      while (s3 == 1)
                      {
                          System.out.println("1.Add New Entry\n2.Existing Medicines List");
                          c1 = input.nextInt();
                          if(c1!=1 && c1!=2)
                          	//throw new Exception("IOException: You have Entered Wrong Choice Program Terminated!");
                        	  System.out.println(" You Have Enter Wrong Choice!!!");
                          switch (c1)
                          {
                              case 1:
                                  {
                                      m[count3].new_medi();count3++;
                                      break;
                                  }
                              case 2:
                                  {
                                      System.out.println("--------------------------------------------------------------------------------");
                                      System.out.println("     Name \t      Company \t\t Expiry Date \t Cost \t Quantity");
                                      System.out.println("--------------------------------------------------------------------------------");
                                      for (j = 0; j < count3; j++) {
                                          m[j].find_medi();
                                      }
                                      break;
                                  }
                          }
                          System.out.println("\nReturn to Back Press 1 and for Main Menu Press 0");
                          s3 = input.nextInt();
                      }
                      break;
                  }
              case 4:
                  {
                      s4 = 1;
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("                    **LABORATORY SECTION**");
                      System.out.println("--------------------------------------------------------------------------------");
                      while (s4 == 1)
                      {
                          System.out.println("1.Add New Entry \n2.Existing Laboratories List");
                          c1 = input.nextInt();
                         // if(c1!=1 && c1!=2)
                          	//throw new Exception("IOException: You have Entered Wrong Choice Program Terminated!");
                          switch (c1)
                          {
                              case 1:
                                  {
                                      l[count4].new_faci();count4++;
                                      break;
                                  }
                              case 2:
                                  {
                                      System.out.println("--------------------------------------------------------------------------------");
                                      System.out.println("      Facilities\t\tCost");
                                      System.out.println("--------------------------------------------------------------------------------");
                                      for (j = 0; j < count4; j++) {
                                          l[j].faci_list();
                                      }
                                      break;
                                  }
                          }
                          System.out.println("\nReturn to Back Press 1 and for Main Menu Press 0");
                          s4 = input.nextInt();
                      }
                      break;
                  }
              case 5:
                  {
                      s5 = 1;
                      System.out.println("--------------------------------------------------------------------------------");
                      System.out.println("          **HOSPITAL FACILITY SECTION**");
                      System.out.println("--------------------------------------------------------------------------------");
                      while (s5 == 1)
                      {
                          System.out.println("1.Add New Facility\n2.Existing Facilities List");
                          c1 = input.nextInt();
                         // if(c1!=1 && c1!=2)
                          	//throw new Exception("IOException: You have Entered Wrong Choice Program Terminated!");
                          switch (c1)
                          {
                              case 1:
                                  {
                                      f[count5].add_faci();count5++;
                                      break;
                                  }
                              case 2:
                                  {
                                      System.out.println("-----------------------------------");
                                      System.out.println("Hospital  Facility are:");
                                      System.out.println("-----------------------------------");
                                      for (j = 0; j < count5; j++) {
                                          f[j].show_faci();
                                      }
                                      break;
                                  }
                          }
                          System.out.println("\nReturn to Back Press 1 and for Main Menu Press 0");
                          s5 = input.nextInt();
                      }
                      break;
                  }
                  case 6:
              	{
              		s6 = 1;
              		System.out.println("--------------------------------------------------------------------------------");
              		System.out.println("                      **BILLING SECTION**");
              		System.out.println("--------------------------------------------------------------------------------");
              		while (s6 == 1)
                       {
              			 System.out.println("1.Add New Bill\n2.Show Existing Bills");
                           c1 = input.nextInt();
                           //if(c1!=1 && c1!=2)
                           	//throw new Exception("IOException: You have Entered Wrong Choice Program Terminated!");
                           switch (c1)
                           {
                               case 1:
                                   {
                                  	 
                                  	 System.out.println("--------------------------------------------------------------------------------");
                                       System.out.println("                     **ENTER PATIENT DETAILS**");
                                       System.out.println("--------------------------------------------------------------------------------");
                                       p[count6].new_patient();
                                  	 b[count6].item_list();
                                  	 b[count6].CalculateTotal(d, count1, m, count3, l, count4, p, count6);
                                  	 count6++;
                                       break;
                                   }
                               case 2:
                                   {
                                  	// inputclass.ip.next();
                                  	 System.out.println("--------------------------------------------------------------------------------");
                                       System.out.println("                     **HOSPITAL BILL DETAILS**");
                                       System.out.println("--------------------------------------------------------------------------------");
                                       System.out.println("--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------");
                                       System.out.println("Billid \t Pid \t\t Pname \t     Dname \t\t Admit Status \t Disease \t Appoint \t Doc Cost \t Med Cost \t LabCost \t Discount \t Total Cost \t Dicounted Cost");
                                       System.out.println("--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------");
                                       for (j = 0; j < count6; j++) {
                                           b[j].bill_info();
                                       }
                                       billing.id = 1001;

                                       break;
                                   }
                           }
                           
                           System.out.println("\nReturn to Back Press 1 and for Main Menu Press 0");
                           s6 = input.nextInt();
                       }
                       break;
              	}
                  case 7:
                  {
                  	System.out.println("ARE YOU SURE TO EXIT(1 TO EXIT)(0 TO CANCEL THE COMMAND)");
                  	int ip = input.nextInt();
                  	if(ip == 1)
                  		System.out.println("Thank you for using Hospital Management System!!!");
                  	
                  		System.exit(0);
                  	break;
                  }
              	default :
                  {
                      System.out.println(" You Have Enter Wrong Choice!!!");
                      break;
                  }

          }
          System.out.println("\nReturn to MAIN MENU Press 1");
          status = input.nextInt();
      }
      input.close();
  
  
}
}

Doctor class:-
package hospital;

import java.util.Scanner;

public class doctor {
	
	String did, dname, specilist, appoint, doc_qual;
    int droom, consult_fee;
    Scanner input = new Scanner(System.in);
    void new_doctor()
    {
        
        System.out.print("Id:-");
        did = input.nextLine();
        System.out.print("Name of Doctor:-");
        dname = input.nextLine();
        System.out.print("Specilization of Doctor:-");
        specilist = input.nextLine();
        System.out.print("Work time of Doctor:-");
        appoint = input.nextLine();
        System.out.print("Qualification of Doctor:-");
        doc_qual = input.nextLine();
        System.out.print("Room no of Doctor:-");
        droom = input.nextInt();
        System.out.print("Consultation fee of Doctor:-");
        consult_fee = input.nextInt();
        //input.close();
    }
    void doctor_info()
    {
        System.out.format("%3s%21s%20s%15s%15s%15s%15s\n",did,dname,specilist,doc_qual,appoint,droom,consult_fee );
    }
    
    
}

Patient class:-
package hospital;

import java.util.Scanner;

public class patient {
	String pid, patname, docname, disease, sex, admit_status;
	int age;
	Scanner input = new Scanner(System.in);
	void new_patient()
	{
		System.out.print("Id:- ");
		if(!input.hasNextInt())
			input.nextLine();
		else
			pid = input.nextLine();
		System.out.print("Patient Name:- ");
		if(input.hasNext("\n"))
			input.nextLine();
		else
			patname = input.nextLine();
		System.out.print("Doctor Name:- ");
		if(input.hasNext("\n"))
			input.nextLine();
		else
			docname = input.nextLine();
		System.out.print("Disease of Patient:- ");
		if(input.hasNext("\n"))
			input.nextLine();
		else
			disease = input.nextLine();
		System.out.print("Gender of Patient of patient:- ");
		if(input.hasNext("\n"))
			input.nextLine();
		else
			sex = input.nextLine();
		System.out.print("Admit Status of Patient:- ");
		if(input.hasNext("\n"))
			input.nextLine();
		else
			admit_status = input.nextLine();
		System.out.print("Age of Patient:- ");
		if(!input.hasNextInt())
			input.nextLine();
		else
			age = input.nextInt();
      //input.close();
  }
  void patient_info()
  {
      System.out.format("%5s%20s%20s%15s%15s%15s%14s\n",pid,patname,docname,disease,sex,admit_status,age);
  }
}

Billing class:-
package hospital;

import java.util.Scanner;

public class billing extends patient{
	int total_cost = 0, labno, medno, medi_cost = 0, munit, doc_cost, lab_cost = 0, billid;
	double dc;
	static int id = 1001;
	String med[][], lablist[], discount, appoint;
	String pid, patname, docname, admit_status, disease;
	Scanner input = new Scanner(System.in);

	void item_list() {
		System.out.print("Enter total no of medicines: ");
		//if(ip.hasNextInt())
		medno = input.nextInt();
		if(medno != 0)
		{
			med = new String[medno][2];
			System.out.println("Enter Medicine names: ");
			for(int i = 0; i < medno; i++)
			{
				System.out.print("Medicine "+ (i+1) +": ");
				med[i][0] =input.next();
				System.out.print("Units of Medicine "+ (i+1) +": ");
				med[i][1] =input.next();
			}
		}
		System.out.print("Enter total no of labs: ");
		labno =input.nextInt();
		if(labno != 0)
		{
			lablist = new String[labno];
			System.out.println("Enter lab names: ");
			for(int i = 0; i < labno; i++)
			{
				System.out.print("Lab "+ (i+1) +": ");
				lablist[i] = input.next();
			}
		}
		//ip.close();
	}
	
	void CalculateTotal(doctor d[], int count1, medical m[], int count2, lab l[], int count3, patient p[], int count) {
		
		pid = p[count].pid;
		patname = p[count].patname;
		docname = p[count].docname;
		admit_status = p[count].admit_status;
		disease = p[count].disease;
		for(int i = 0; i < count1; i++)
		{
			if(d[i].dname.equals(p[count].docname))
			{
				doc_cost = d[i].consult_fee;
				appoint = d[i].appoint;
				total_cost += doc_cost;
				break;
			}
		}
		
		System.out.println("\n");
		if(medno != 0)
			for(int i = 0; i < medno; i++)
			{
				for(int j = 0; j < count2; j++)
				{
					if(m[j].med_name.equals(med[i][0]))
					{
						if(m[j].count == 0)
						{
							System.out.println(med[i] + " is out of stock");
							break;
						}
						munit = Integer.parseInt(med[i][1]);
						if(munit <= m[j].count)
						{
							m[j].count -= munit;
							medi_cost += m[j].med_cost*munit;
						}
						else
						{
							System.out.print("We only have " + m[j].count + " units of " + m[j].med_name + " only");
							medi_cost += m[j].med_cost*m[j].count;
							m[j].count = 0;
						}
						break;
					}
					if((j == count2-1) && (m[j].med_name != med[i][0]))
						System.out.println(med[i] + " is out of stock");
				}
			}
		total_cost += medi_cost;
		
		if(labno != 0)
			for(int i = 0; i < labno; i++)
			{
				for(int j = 0; j < count3; j++)
				{
					if(l[j].facility.equals(lablist[i]))
					{
						lab_cost += l[j].lab_cost;
						break;
					}
				}
			}
		total_cost += lab_cost;
		System.out.println();
		if(total_cost <= 0)
			System.out.println("Enter correct details");
		else if(total_cost < 500)
		{
			discount = "3%";
			System.out.println("Total Cost is: "+total_cost);
			System.out.println("Discount(Bill below 500): 3%");
			dc = 0.97 * total_cost;
			System.out.format("Dicounted Total Cost is: %5.2f\n",dc);
		}
		else if(total_cost < 1000)
		{
			discount = "4%";
			System.out.println("Total Cost is: "+total_cost);
			System.out.println("Discount(Bill below 1000 but above 500): 4%");
			dc = 0.96 * total_cost;
			System.out.format("Dicounted Total Cost is: %5.2f\n",dc);
		}
		else if(total_cost < 1500)
		{
			discount = "5%";
			System.out.println("Total Cost is: "+total_cost);
			System.out.println("Discount(Bill below 1500 but above 1000): 5%");
			dc = 0.95 * total_cost;
			System.out.format("Dicounted Total Cost is: %5.2f\n",dc);
		}
		else
		{
			discount = "10%";
			System.out.println("Total Cost is: "+total_cost);
			System.out.println("Discount(Bill above 1500): 10%");
			dc = 0.9 * total_cost;
			System.out.format("Dicounted Total Cost is: %5.2f\n",dc);
		}
	}
	
	void bill_info()
	{
		billid = id;
		System.out.format("%5s%5s%20s%20s%10s%20s%15s%15s%15s%15s%20s%15s\t\t    %5.1f\n",billid,pid,patname,docname,admit_status,disease,appoint,doc_cost,medi_cost,lab_cost,discount,total_cost,dc);
		id++;
	}
}

Facility Class:-
package hospital;

import java.util.Scanner;

public class facility {
	String fac_name;
	Scanner input = new Scanner(System.in);
    void add_faci()
    {
        
        System.out.print("Facility for Hospital:-");
        fac_name = input.nextLine();
        input.close();
    }
    void show_faci()
    {
        System.out.println(fac_name);
    }
}

Lab class:-
package hospital;

import java.util.Scanner;

public class lab {
	String facility;
    int lab_cost;
    Scanner input = new Scanner(System.in);
    void new_faci()
    {
        
        System.out.print("facility:-");
        facility = input.nextLine();
        System.out.print("cost:-");
        lab_cost = input.nextInt();
        //input.close();
    }
    void faci_list()
    {
        System.out.format("%15s%20s\n",facility,lab_cost);
    }
}

Medical class:-
package hospital;


import java.util.Scanner;

public class medical {
	String med_name, med_comp, exp_date;
    int med_cost, count;
    Scanner input = new Scanner(System.in);
    void new_medi()
    {
        
        System.out.print("Name of Medicine:-");
        med_name = input.nextLine();
        System.out.print("Company of Medicine:-");
        med_comp = input.nextLine();
        System.out.print("Exp_date of Medicine:-");
        exp_date = input.nextLine();
        System.out.print("Cost of Medicine:-");
        med_cost = input.nextInt();
        System.out.print("No of unit of Medicine:-");
        count = input.nextInt();
        //input.close();
    }
    void find_medi()
    {
        System.out.format("%10s%20s%20s%10s%10s\n",med_name,med_comp,exp_date,med_cost,count);
    }
}


Output:-
![image](https://user-images.githubusercontent.com/64677848/139654848-dd8515d2-16fc-4bdd-9a6a-146e79340408.png)
![image](https://user-images.githubusercontent.com/64677848/139654991-b66dff20-9313-41c9-9573-516e638d6782.png)
![image](https://user-images.githubusercontent.com/64677848/139655219-8e572416-f7f0-479e-b3f8-bbedf1c5442c.png)
![image](https://user-images.githubusercontent.com/64677848/139655317-bee2aa2e-fdb5-4c6a-a644-cca7e79ca094.png)
![image](https://user-images.githubusercontent.com/64677848/139655583-a21b0dae-9c9e-443d-8791-145bf474b9bb.png)
![image](https://user-images.githubusercontent.com/64677848/139656191-1b9ae3d4-c76b-49eb-87fa-5bcdcb3db4b4.png)
![image](https://user-images.githubusercontent.com/64677848/139656239-95580160-8143-426c-9daf-912abcfc8b01.png)







