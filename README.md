# JavaConfig
Configure db.properties file on src/resources

DAOImpl class must include SessionFactory method

below is test file


package com.demo.app;

import java.util.List;

import org.springframework.context.annotation.AnnotationConfigApplicationContext;
import com.demo.app.model.Customer;
import com.demo.app.service.CustomerService;
import com.demo.config.AppConfig;

public class CustomerTest {

	public static void main(String[] args) {
		 AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);	 
		 CustomerService cs = context.getBean(CustomerService.class);
		 //get Customers
		 List<Customer> c = cs.getAllCustomer();
	      for (Customer user : c) {
	         System.out.println("Id = "+user.getCustID());
	         System.out.println("Full Name = "+user.getFullname());
	         System.out.println("Country = "+user.getCountry());
	      
	         System.out.println();
	      }

	      context.close();
	   }


}


