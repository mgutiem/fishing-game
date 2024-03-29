# Fishing Game 
 A fishing game developed in C# console application

## Copyright Disclaimer / Student Warning
_I developed this project for the C# II course part of the UCLA Applications Programming Certificate._

_If you're a student currently enrolled to this course feel free to review my code **but only as a reference or for study purposes.**_

***DO NOT copy my code or hand it in as yours***, _professor has all the records of each one of our previous delivered works, so he will know it and you'll undoubtedly get in trouble for plagiarism._

## Features

1. Players 
    - Start with $0 cash.
    - Makes money selling fish. Players then use the money to buy better fishing rods to catch better fish.
    - Start with bamboo stick fishing rod. Costs $0 with +0 buff
2. Sell fish
    - Automatically sells all of user's fish in container. 
    - Prices based on standard market price assigned to each fish (set inside Fish's subclass).
    - If container is empty, tell player to come back when you have fish.
3. Bass pro shop
    - Print how much money players have at the top.
    - Print the rods available on sale.
    - Verify player has enough money to purchase rod.
    - Allow player to buy rod if sufficient money.
    - Fishing rods add buffs to help them catch more fish. 

> Example: Suppose there's 30% chance of catching catfish. If I have a rod with +10 buff, that means there'll be 40% chance of catching catfish. Buff works on all fishes.

4. Go fishing
    - Ask users what lake they want to go to.
    - Depending on the lake they go to, there will be different fishes and probabilities.
    - Print all fish caught in the container. 
5. Fish marketplace value
    - Catfish: $10
    - Bluefin: $500
    - Albacore: $50
    - Yellowtail: $100

 
## How it works
1. Lake class has these parameters: 
    - Name
    - List of fish available in the lake and their probabilities.
2. Fish class has these parameters:
    - Probably of being caught
3. FishingRod class has these parameters:
    - Name
    - Price
    - Buff
 

```CSHARP
// list of lakes
List<Lake> all_lakes = new List<Lake>()
{
    // each lake takes in a list of fish that's available in the lake
    new Lake("Lake Tahoe", new List<Fish>()
    {
        // each fish takes in the probability they bite the bait. So catfish has 35% chance of biting
        new Catfish(35),

        // albacore has 20% chance of biting
        new Albacore(20),

        // bluefin has 5% chance of biting
        new Bluefin(5)

    }),
    // each lake takes in a list of fish that's available in the lake
    new Lake("Big Bear lake", new List<Fish>()
    {
        // catfish less prolific in big bear, only 30% chance of biting.
        new Catfish(30),

        // albacore has 35% chance of biting
        new Albacore(35),

        // yellowtail has 15% chance of biting
        new YellowTail(15),

    })
};

// list of all fishing rods available at the store
List<FishingRod> all_rods = new List<FishingRod>()
{
    // each fishing rod passes in the name, price, and buff added to probability.
    new FishingRod("Swift Model E", 50, 2),
    new FishingRod("Perry Water Eye Gouger", 200, 6),
    new FishingRod("The Senator", 400, 10),
    new FishingRod("Ocean Depleter", 1000, 20),

};
