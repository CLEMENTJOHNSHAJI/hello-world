# hello-world
Another repository
package fi.oulu.tol.sqat.tests;

import static org.junit.Assert.*;

import java.util.ArrayList;
import java.util.List;

import org.junit.Test;

import fi.oulu.tol.sqat.GildedRose;
import fi.oulu.tol.sqat.Item;

public class GildedRoseTest {

// Example scenarios for testing
//   Item("+5 Dexterity Vest", 10, 20));
//   Item("Aged Brie", 2, 0));
//   Item("Elixir of the Mongoose", 5, 7));
//   Item("Sulfuras, Hand of Ragnaros", 0, 80));
//   Item("Backstage passes to a TAFKAL80ETC concert", 15, 20));
//   Item("Conjured Mana Cake", 3, 6));

	@Test
	public void testUpdateEndOfDay_AgedBrie_Quality_10_11() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Aged Brie", 2, 10) );
		
		// Act
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(11, itemBrie.getQuality());
	}
    
	@Test
	public void testUpdateEndOfDay() {
		fail("Test not implemented");
	}
	
	@Test
	public void testUpdateEndOfDay_Elixir_of_the_Mongoose_Vest_Quality_10_30() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Elixir of the Mongoose", 10, 30) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(27, itemBrie.getQuality());
	}
	
	@Test
	public void testUpdateEndOfDay_Dexterity_Vest_Quality_10_20() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Dexterity Vest", 10, 20) );
		
		// Act
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(19, itemBrie.getQuality());
	}
	@Test
	public void testUpdateEndOfDay_Sulfuras_10_80() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Sulfuras", 10, 80) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(80, itemBrie.getQuality());
		// Sulfuras is getting error
	}
	
	@Test
	public void testUpdateEndOfDay_Conjured_Mana_Cake_Quality_6_10() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Conjured Mana Cake", 6, 10) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(6, itemBrie.getQuality());
		assertEquals(2, itemBrie.getSellIn());
	}
	
	@Test
	public void testUpdateEndOfDay_Backstage_passes_Quality_12_20() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Backstage passes",12, 20) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(26, itemBrie.getQuality());
		assertEquals(8, itemBrie.getSellIn());
	}
	
	@Test
	public void testUpdateEndOfDay_Backstage_passes_Qualityincreases_by_3_6_20() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Backstage passes",6, 20) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
		store.updateEndOfDay();
		
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(28, itemBrie.getQuality());
		assertEquals(3, itemBrie.getSellIn());
	}
	
	@Test
	public void testUpdateEndOfDay_Conjured_Mana_Cake_Quality_1_1() {
		// Arrange
		GildedRose store = new GildedRose();
		store.addItem(new Item("Conjured Mana Cake", 1, 1) );
		
		// Act
		store.updateEndOfDay();
		store.updateEndOfDay();
	
		
		// Assert
		List<Item> items = store.getItems();
		Item itemBrie = items.get(0);
		assertEquals(0, itemBrie.getQuality());
		
	}
}
