package application;

import java.util.ArrayList;
import java.util.List;

import entities.Product;

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("TV", 900.00));
		list.add(new Product("Notebook", 1200.00));
		list.add(new Product("Tablet", 450.00));

		list.sort((p1, p2) -> p1.getName().toUpperCase().compareTo(p2.getName().toUpperCase()));
		/*
		 * eu to chamando o list.sort, e como argumento do meu sort, eu coloquei yma expressão lambida, que é uma função
		 * anonima, que eu posso definila de uma forma bem resumida.
		 * isso aqui é um comparator definido com a sintaxe de expressão lambida.
		 * (p1, p2) levando(->) a uma implementação de função. 
		 * aqui na hora de fazer a expressão lambda, eu não precisei declarar aqui essa variavel p1 e p2, elas são do 
		 * tipo product, aqui o proprio compilador fez a inferencia dos tipos, ele deduzio que os tipos desssas variaveis 
		 * aqui são product, então é isso aqui que a gente chamamos de inferencia de tipos 
		 */

		for (Product p : list) {
			System.out.println(p);
		}
	}
}	

===========================================================================

package entities;

public class Product {

	private String name;
	private Double price;
	
	public Product() {
	}

	public Product(String name, Double price) {
		this.name = name;
		this.price = price;
	}

	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public Double getPrice() {
		return price;
	}

	public void setPrice(Double price) {
		this.price = price;
	}

	@Override
	public String toString() {
		return "Product [name=" + name + ", price=" + price + "]";
	}
}

