```java
public enum Rank {
    THREE("3", 3),
    FOUR("4", 4),
    FIVE("5", 5);

    private final String label;
    private final int value;
    Rank(String label, int value) {
        this.label = label;
        this.value = value;
    }

    @Override
    public String toString() {
      return label;
    }
}
```

```java
public enum Suit {
    SPADE,
    DIAMOND,
    CLUB,
    HEART;

    private final String label;
    Suit(String label) {
        this.label = label;
    }

    @Override
    public String toString() {
      return label;
    }
}
```

```java
public class Card {

    private final Rank rank;
    private final Suit suit;

    public Card(Suit suit, Rank rank) {
        this.rank = rank;
        this.suit = suit;
    }

    @Override
    public String toString() {
        return suit.toString() + rank.toString();
    }
} 
```

```java
import java.util.ArrayList;
import java.util.List;

public class Deck {

    static final List<Card> CARDS = getCARDS();
    // { [heart 1], [], [], [], ..., [] } -> one array of cards
    // { [], [], [], ... , [] } -> another array of cards
    // CARDS[0] = new Card(Suit.SPADE, RANK.FIVE);
    // CARDS = new Card[52]; !!! ERROR !!!

    private List<Card> dealPile = new ArrayList<>();
    private List<Card> discardPile = new ArrayList<>();

    static List<Card> getCARDS() {
        List<Card> cards = new ArrayList<>();

        for (Suit suit: Suit.values()) {
            for (Rank rank: Rank.values()) {
                cards.add(new Card(suit, rank));
            }
        }
        // Done initialize CARDS
        return cards;
    }

    private void initializePiles {
        dealPile.clear();
        dealPile.addAll(CARDS);
        discardPile.clear();
    }

    public Deck() {
        initializePiles();
    }

    public Deck shuffle() {
        Collections.shuffle(dealPile);
        return this;
    }

    public Deck reset() {
        dealPile.addAll(discardPile);
        discardPile.clear();
        return this;
    }

    public Card deal() {
        // remove top element from dealPile
        // And add the removed element to discardPile
        // And return the element
        
        Card card = dealPile.remove(0);
        discardPile.add(card);
        return card;
    }

    public List<Card> deal(int num) {
        List<Card> cards = new ArrayList<>();
        for (int i = 0; i < num; i++) {
            cards.add(deal());
        }
        return cards;
    }
}
```
```java
import java.util.Scanner;

public class Game {

    private final Scanner scanner = new Scanner(System.in);

    private String getUserInput(Set validInputs) {
        while (true) {
            String input = scanner.nextLine().toLowerCase();

            if (validInputs.contains(input)) {
                return input;
            } else {
              System.out.println("Invalid Input! Please Try Again!");
            }
        }
    }

    public void mainLoop() {
        System.out.println("Start A New Game!");
        Deck dec = new Deck();
        do {
          // do gaming...
          // deal two cards
          // hit: deal 1 card
          // stand: stop dealing
          // double
          // bet

          // Player: capital, makeAction

          System.out.println("Do You Want To Continue? (Yes/No)");
        } while (getUserInput(Set.of("Yes", "No")).equals("Yes"));
    }
}
```
```java
public class Main {

    public static void main(String[] argv) {
        Game game = new Game();
        game.mainLoop();
    }
}
```
