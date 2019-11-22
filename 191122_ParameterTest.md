````java
package junit;

import static org.junit.Assert.assertTrue;

import java.util.EnumSet;
import java.util.concurrent.TimeUnit;
import java.util.stream.Stream;

import org.junit.jupiter.params.ParameterizedTest;
import org.junit.jupiter.params.provider.CsvFileSource;
import org.junit.jupiter.params.provider.CsvSource;
import org.junit.jupiter.params.provider.EnumSource;
import org.junit.jupiter.params.provider.MethodSource;
import org.junit.jupiter.params.provider.ValueSource;

public class ParameterTest {
//	@ParameterizedTest
//	@ValueSource(strings = { "racecar", "radar", "able was I ere I saw elba" })
//	public void testWithValueSource(String argument) {
//		System.out.println(argument);
//	}
	
//	@ParameterizedTest
//	@EnumSource(value = TimeUnit.class , names = { "DAYS", "HOURS" })
//	void testWithEnumSourceInclude(TimeUnit timeUnit) {
////	    assertTrue(EnumSet.of(TimeUnit.DAYS, TimeUnit.HOURS).contains(timeUnit));
//	System.out.println(timeUnit);
//	}
	
//	@ParameterizedTest
//	@MethodSource("stringProvider")
//	void testWithExplicitLocalMethodSource(String argument) {
//	   System.out.println(argument);
//	}
//	static Stream<String> stringProvider() {
//	    return Stream.of("apple", "banana");
//	}

//	@ParameterizedTest
//	@CsvSource({
//	    "apple,         1",
//	    "banana,        2",
//	    "'lemon, lime', 3"
//	})
//	void testWithCsvSource(String fruit, int rank) {
//	    System.out.println(fruit);
//	    System.out.println(rank);
//	}
//	
	@ParameterizedTest
	@CsvFileSource(resources = "two-column.csv", numLinesToSkip = 1)//跳过第一行
	void testWithCsvFileSource(String country, int reference) {
	    System.out.println(country);
	    System.out.println(reference);
	}
	
}
````
