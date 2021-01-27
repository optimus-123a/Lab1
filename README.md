# Lab1
It is just my homework

public class Example1 {

    //#12 Створіть метод, який сортує будь який масив int[] методом вставок.
    public static void insertionSort(int[] array) {
        for (int i = 1; i < array.length; i++) {
            int current = array[i];
            int j = i - 1;
            while(j >= 0 && current < array[j]) {
                array[j+1] = array[j];
                j--;
            }
            array[j+1] = current;
        }
    }

    //#16 Створіть метод, який дозволяє на вхід прийняти слово українською, а повернути слово в латиницу, яке приблизно звучить як українське. Наприклад - на вхід подаємо слово -= щастя = на виході отримуємо =shastia=
    public static String transliterate(String message){
        char[] abcCyr =   {' ','а','б','в','г','д','е','ж','з','и','і','й','к','л','м','н','о','п','р','с','т','у','ф','х', 'ц','ч', 'ш','щ','ь','э', 'ю','я','А','Б','В','Г','Д','Е','Ё', 'Ж','З','И','І','Й','К','Л','М','Н','О','П','Р','С','Т','У','Ф','Х', 'Ц', 'Ч','Ш', 'Щ','Ь','Э','Ю','Я'};
        String[] abcLat = {" ","a","b","v","g","d","e","zh","z","i","i", "y","k","l","m","n","o","p","r","s","t","u","f","h","ts","ch","sh","sch","","e","ju","ja","A","B","V","G","D","E","E","Zh","Z","I", "I","Y","K","L","M","N","O","P","R","S","T","U","F","H","Ts","Ch","Sh","Sch", "","E","Ju","Ja"};
        StringBuilder builder = new StringBuilder();
        for (int i = 0; i < message.length(); i++) {
            for (int j= 0; j < abcCyr.length; j++ ) {
                if (message.charAt(i) == abcCyr[j]) {
                    builder.append(abcLat[j]);
                }
            }
        }
        return builder.toString();
    }

    //20 Створіть метод, який може підрахувати кількість голосних букв у будь якому слові (мова українська)
    public static int valueOfVowels(String word){
        int wordscounter=0;
        char[] vowels = {'а', '0', 'у', 'е', 'и', 'і', 'я', 'ю', 'є','ї'};
        for(int i=0; i<word.length(); i++){
            for(int j=0; j<vowels.length; j++){
                if(word.charAt(i)==vowels[j]){
                    wordscounter++;
                }else{
                    continue;
                }
            }
        }
        return wordscounter;
    }

    //#26 Створіть метод, який приймає параметр int та конвертує його з десятичної у двоічну систему обчислення та повертає у вигляді String. Приклад- приймає 4, повертає =0b10=
    public static String binarStringCovertor (int a) {
        StringBuilder value = new StringBuilder();
        value.append(Integer.toBinaryString(a));
        return value.toString();
    }

    //Я знав про існування методів конвертації в різні системи числення,
    //але в завданні було чітко вказано СТВОРІТЬ МЕТОД, тому я його й написав.

    //#27 Створіть метод, який приймає параметр int та конвертує його з десятичної у двоічну систему обчислення та повертає у вигляді String. Приклад- приймає 4, повертає =0b10=
    public static String octalStringConvert(int a){
        StringBuilder value = new StringBuilder();
        value.append(Integer.toOctalString(a));
        return value.toString();
    }

    //Практичні завдання:
    public static String teorTestBinar(int a) {
        int b;
        StringBuilder value1 = new StringBuilder();
        while(a !=0 ) {
            b = a%2;
            value1.append(b);
            a = a/2;
        }
        value1.reverse();
        return value1.toString();
    }

    public static String  teorTestOctal(int a){
        int b;
        StringBuilder value1 = new StringBuilder();
        while(a !=0){
            b=a%8;
            value1.append(b);
            a=a/8;
        }
        value1.reverse();
        return value1.toString();
    }

    public static void main(String[] args) {
        int[]array = {6, 2, 3, 4, 5, 1};
        insertionSort(array);
        for(int i=0; i<array.length; i++)  {
            System.out.print(array[i]+", ");
        }

        System.out.println();

        String str="Привіт світ!";
        System.out.println(transliterate(str));

        String word="Привіт";
        System.out.println(valueOfVowels(word));

        System.out.println(binarStringCovertor(4));

        System.out.println(octalStringConvert(9));

        System.out.println(teorTestOctal(259));
    }
}
