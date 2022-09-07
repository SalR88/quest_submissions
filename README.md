# Quest Submissions

Septemeber 2022 Emerald City Bootcamp - Beginner Cadence Course

----------

Chapter 1, Day 1


--Blockchain is a decentralized database that anyone can view and interact with. 

--A smart contract is data that stores parameters and makes changes to the blockchain with a function that anyone can call. 

--A transaction is a paid function call that changes the data on the blockchain and costs money depending on which blockchain you are on.
A script only views the blockchain and cannot make changes to it and doesn't cost money. 

----------

Chapter 1, Day 2

What are the 5 Cadence Programming Language Pillars?

    --Safey and security, clarity, approachability, developer experience, resource oriented programming

In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)?

    --The 5 pillars could be useful for the overall experience of the blockchain to be a good experience. 


-----

Chapter 2, Day 1 

```cadence
pub contract JacobTucker {

    pub let is: String

    init() {
        self.is = "the best"
    }
}

//15:53:40  Deployment  Deployed Contract To: 0x03
```

-----

Chapter 2, Day 2

Please answer in the language of your choice.

Explain why we wouldn't call changeGreeting in a script.

    --Scripts can't make changes, only view   

What does the AuthAccount mean in the prepare phase of the transaction?

    --access information in account

What is the difference between the prepare phase and the execute phase in the transaction?

    -prepare phase is to view and access account information and execute phase uses functions to make changes to the blockchain

This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

Add two new things inside your contract:

A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber
Add a script that reads myNumber from the contract

Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.

#Contract

```cadence
pub contract NumberQuest{

    pub var myNumber: Int



    pub fun number(): Int {
        return self.myNumber
    }


    pub fun updateMyNumber() {
        self.myNumber = 1
    }

    init() {
        self.myNumber = 0
    }

   

}
```

#Script

```cadence
import NumberQuest from 0x01

pub fun main() {
    log(NumberQuest.number())
    }
```

#Transaction

```cadence
import NumberQuest from 0x01

transaction() {
    prepare(signer: AuthAccount) {
    log(signer.address)
    }

    execute {
      NumberQuest.updateMyNumber()
    }
}
```
-----------------

Chapter 2 Day 3

In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

#Script for example Array
```cadence
pub fun main() {
    var favoritepeople: [String] = ["L", "M", "S"]
    log(favoritepeople)
  }
```

In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

#script for example dictionary 
```cadence
pub main() {
    var socialMedia: {String: Int} = {"reddit":2, "instagram": 1, "youtube": 3, "facebook": 0, "twitter": 0}
    log(socialMedia.keys)
}
```

Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).

#Force-unwrap example
pub fun main(): String {
    let thing: {String: Int} = {"Hi": 1, "Bonjour": 2, "Hola": 3}
    return thing[1]!
    
    //the force-unwrap operator is returning the thing we put from the optional, this example returns "Hi"
    
    
    
Using this picture below, explain...

What the error message means
Why we're getting this error
How to fix it

-When you access elements of a dictionary, it returns the value as an optional. so it may be Int or it may be nil. using a force-unwrap operator would fix this error. Returning an optional would be better that using a force-wrap operator because it won't abort if nil is returned. 

  
    
    
---------------------

  
