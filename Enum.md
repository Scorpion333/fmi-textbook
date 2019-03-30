# Enum

Enum-ът е тип данни. Тип данни, за който има само няколко възможни стойности.

Синтаксисът е много лесен. Примерни enum-и:

    enum Weekday {
        Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday
    };

    enum Suite {
        Clubs, Diamonds, Hearts, Spades
    };

    enum Gender {
        Male, Female
    };

## Работа с enum

Даването на стойност става по "стандартния начин":

    Weekday d;
    d = Monday;
    d = Tuesday;

Ако искаме да проверим каква стойността на някоя променлива, най-просто е да я сравним с всяка възможна стойност:

    if(day == Monday) {
        cout << "It's Monday";
    }
    else if(day == Tuesday) {
        cout << "It's Tuesday";
    }
    // ...
    else if(day == Sunday) {
        cout << "It's Sunday";
    }

## cin и cout

Нека имаме enum MyEnum с N възможни стойности. Да номерираме стойностите от 0 до N-1 по реда на изписването им.

cin и cout работят така:

    MyEnum x;
    cin >> x;       // Въвеждаме число k, което е номер на някоя от стойностите,
                    // т.е. нещо от 0 до N-1
    
    cout << x;      // Извежда се число - номера на стойността на x
    
Пример: В Suite Clubs e стойност номер 0, Diamonds е номер 1, Hearts е номер 2, Spades е номер 3.

    Suite suite;
    cin >> suite;   // Да кажем, че въвеждаме 2. suite става стойност номер 2, т.е. Hearts

    cout << suite;  // 2
                    // Защото suite e Hearts, т.е. стойност номер 2 от Suite
    
## Защо така?

Маниаците, написали С++, не са били много креативни с enum-ите, затова са решили, че един enum ще е просто списък с константи
от тип int.

    enum Suite {
        Clubs, Diamonds, Hearts, Spades
    };

работи по начин, подобен на това:

    const int Clubs = 0;
    const int Diamonds = 1;
    const int Hearts = 2;
    const int Spades = 3;

    class Suite {
        int number;
    public:
        // Класът работи точно като int, само че при опит за промяна на стойността,
        // се проверява дали тя от 0 до 3
    };
