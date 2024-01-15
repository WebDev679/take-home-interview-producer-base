# Take home assessment

- [x] Implement warrants feature
- [x] UI simplification
- [x] Leaderboard
- [x] Data Analysis
- [x] Minor bug fixes
      
Documentation:

In this modified code base, I have added the warrants feature (which includes the ability to add a warrant and challenge a competitor), redesigned the UI a bit to be more simplistic, added a leaderboard, and written Python code in a notebook to analyze the extracted data and present it in a friendly and understandable manner.

To run the Python code, you have to first run the following command in your Empirica project directory

`empirica export`

This will make a zip file in your project directory. Open up the zip file and go to “players.csv”. 

Change the file path in the notebook to the file path of this file. 

Then you install the following Python libraries if you do not have them already. These libraries include numpy, pandas, matplotlib, and seaborn. 

And then you can run the code on the notebook to see the results. 

I have also made some other minor changes, improvements, and bug fixes to the existing code base. 

I have highlighted and discussed all these changes in the demo video below. 

https://drive.google.com/file/d/12FAustPEaWLJiRflD1Ebdr92jg3o6Vjo/view?usp=sharing


## Short Answer 1

I initially spent time to familiarize myself with the existing codebase by reviewing the Empirica documentation, going through the walkthrough video, and testing and running the existing code. This ensures I understand how the whole software works and what changes are necessary to add the new feature. 

Then, I continued on to defining the warrant feature. The warrant feature feature allows producers to vouch for the accuracy of their advertisements by staking a sum of money. If a competitor challenges the advertisement and the claim is found to be false, the staked money is forfeited. However, for now, I added an additional fine on the producer in case the warrant is challenged and the claim is false. A warrant can be challenged by a producer or a consumer. Producers will have the ability to challenge their competitors and as of now, consumers’ challenges, are just calculated randomly using a value of 30% challenge rate.

To make sure that the user is able to navigate through the interface easily, the warrant feature option is simplistic. There is a clear option for producers to add a warrant to their advertisement. There are buttons to select whichever field they want to select and the UI only shows these options when the user has enough money to put at stake for the warrant. This is to ensure that the score does not become negative at any point. 

Other than that, another task to be completed in this feature is the producer’s ability to challenge their competitors’ warrants. This feature should only work in a game with more than one player and should list all the producers with warrants and their advertisements. There is a small fee to challenge someone else’s warrant. 

One of the most important tasks to be planned in this process is the architecture surrounding this feature. The ability to add the warrant should be handled in Advertisement.jsx itself and the score calculation and “challenges” by consumers should be calculated in Results.jsx. The ability to challenge a competitor needs to have its separate stage. Having a separate stage in the same round rather than having a separate round makes retrieving some information easier.

Intense testing is needed to ensure the feature is working as intended. Testing of the feature in Solo, 2-player, and 3-player modes should be tested to make sure it works in all environments and all edge cases should also be tested out. 

For reference purposes, I researched a bit about warrants in virtual marketplaces and primarily just went through the Empirica documentation and looked at some tutorials to get a good idea of the software. 



## Short Answer 2

I think this feature is reflective of a real-world marketplace because there are incentives and trade-offs for every user in this. The producer can stake their money to get access to a larger user base and gain their trust with a warrant. They do this while risking losing more money if their claim is false. Thus, you get a benefit with a trade-off. The same can be said of a competitor challenging another producer. They are not directly gaining anything from the challenge although to come at the top of the market, they will try to keep their competitor’s sales low and this is one way of doing so at a price. This reflects a realistic scenario as you cannot just challenge an advertisement for free in the real world. You might need to incur some costs for filing complaints and processing and that is what this represents. Again, the producer gets an indirect benefit with a trade-off. All this reflects the workings of any real-world marketplace where you have to invest or put something at stake to get a benefit in your business as a producer. 

The trade-offs of the features and the UI that I had to consider to make it as user-friendly as possible are listed below. 

-	I had to make sure that the concept of warrants should be easy to understand for all users. Overly complex mechanisms might deter producers from using the feature.
-	The feature should seamlessly integrate with the current user experience without making it seem that the feature is out of place compared to the rest of the features and UI. 
-	The new stage should have a simplistic UI of challenging other producers and should provide any information that the user needs to decide whether they want to challenge the producer or not. 
-	The amount at stake must be carefully decided. Too high a risk might discourage producers from using the warrant, while too low might not adequately ensure advertisement accuracy. Thus, for now, I have set the amount of adding a warrant be $300 with an additional fine of $500 if a false claim is challenged. I have also set the cost of challenging another producer as $50 so that producers do not just keep challenging everyone without giving it a thought. 

It's very important to find the perfect representation of a real-world marketplace using a perfect balance of trade-offs and benefits to implement this feature successfully. It is also important to make it as simplistic, user-friendly, and engaging as possible.

## UI Redesign

Some other resdesign ideas other than the changes I have made to the UI are listed below. 

The primary goal is to have an easy to use and navigate UI. 

- The leadeboard position should change on the results page and should also show up on the advertise page. 
- The challenge page can list the players in separate block card rather than a list to make it easier to identify other users and navigate.
- The results page can be more condensed and easy to read. To do this, we can have a pop up on the results page that announces all the important information. This ensures that the user knows whether they were challenged, their final score, and all other important information. In the current UI, it is easy to miss information. 

## Data Analysis 

The python notebook is named analysis.ipynb and is in the root folder of the repository. 
