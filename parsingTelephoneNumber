package ru.prackitum;

import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;

public class parsingTelephoneNumber {

    public static void main(String[] args) {

        // ТЕСТЫ
        System.out.println(parseNumber("+7-926-FLOWERS"));
        System.out.println(parseNumber("FJDIJFFll22--"));
        System.out.println(parseNumber("  ++2551JUYADX"));
        System.out.println(parseNumber("+gdfg6652134"));
        System.out.println(parseNumber("+555-333---42"));
        System.out.println(parseNumber("jsdРОССИЯ787"));
        System.out.println(parseNumber("WWWWWWWWWWWWWW"));

    }

    public static String parseNumber(String telephoneNumber) {

        // Заполнение словаря
        HashMap<char[], Character> hashMap = new HashMap<char[], Character>() {{

            put(new char[]{'A', 'B', 'C',}, '2');
            put(new char[]{'D', 'E', 'F',}, '3');
            put(new char[]{'G', 'H', 'I',}, '4');
            put(new char[]{'J', 'K', 'L',}, '5');
            put(new char[]{'M', 'N', 'O',}, '6');
            put(new char[]{'P', 'Q', 'R', 'S'}, '7');
            put(new char[]{'T', 'U', 'V',}, '8');
            put(new char[]{'W', 'X', 'Y', 'Z'}, '9');

        }};

        // Очистка и сборка номера
        return getGoodNumber(telephoneNumber.toUpperCase().replaceAll("[^\\da-zA-Z]",""), hashMap);

    }

    private static String getGoodNumber(String telephoneNumber, HashMap<char[], Character> hashMap) {

        StringBuilder number = new StringBuilder();

        // Сортировка для бинарного поиска не нужна массив уже отсортирован
        char[] arrayNumbers = {'1', '2', '3', '4', '5', '6', '7', '8', '9'};

        // обходим в коллекции все символы номера. Если это цифра тогда добавляем сразу иначе ищем в словаре
        for (char charNumber :
                telephoneNumber.toCharArray()) {

            if (Arrays.binarySearch(arrayNumbers, charNumber) >= 0) {

                // Это цифра
                number.append(charNumber);

            } else {

                // Это буква
                for (Map.Entry<char[], Character> stringEntry : hashMap.entrySet()) {

                    if (Arrays.binarySearch(stringEntry.getKey(), charNumber) >= 0) {

                        number.append(stringEntry.getValue());
                        break;

                    }

                }

            }

        }

        return number.toString();
    }
}
