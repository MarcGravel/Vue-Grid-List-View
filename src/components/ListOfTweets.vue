<template>
    <div id="mainContainer">
        <div id="toggleContainer">
            <label id="theToggle" for="toggleBtn">
            <!--checks button state and applies correct label-->
                <span v-if="!btnState">Click to see List view</span>
                <span v-if="btnState">Click to see Card view</span>
            <!--toggle button for view state-->
        </label>
        <input type="checkbox" id="toggleBtn" @click="isActive()">
        </div>
        <div id="postContainer" :class="{postContainerCard: !btnState}">
            <!--sets class dependant on if btnState is true or false-->
            <div id="singlePost" :class="{listViewContainer: btnState, cardViewContainer: !btnState}" v-for="tweet in tweets" :key="tweet.user">
                <h2 :class="{listViewContent: btnState, cardViewContent: !btnState}">{{tweet.content}}</h2>
                <h4 :class="{listViewUser: btnState, cardViewUser: !btnState}">{{tweet.user}}</h4>
                <h6 :class="{listViewDate: btnState, cardViewDate: !btnState}">{{tweet.date}}</h6>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      name: "ListOfTweets",
      data: () => {
          return {
              btnState: false,
              tweets: [
                  {
                      content: "Sick of having to go to 2 different huts to buy pizza and sunglasses.",
                      user: "@Leemanish",
                      date: "03-24-2013"
                  },
                  {
                      content: "*joins a conga line* ME: I can leave any time I like. *someone joins behind* ME: oh no",
                      user: "@HansGrubertron",
                      date: "03-10-2019"
                  },
                  {
                      content: "How much for the horse tornado? Sir, thats a carousel.. I must have it.",
                      user: "@neonsinatra",
                      date: "02-26-2013"
                  },
                  {
                      content: "'Anybody named Jeff?' JEFF: Yes. GEOFF: Yeos.",
                      user: "@mtobey",
                      date: "01-20-2016"
                  },
                  {
                      content: "The most cutting thing you can say is 'who's this clown?' because it implies they're a) a clown & b) not even one of the better-known clowns",
                      user: "@skullmandible",
                      date: "12-12-2013"
                  },
                  {
                      content: "ME: Can you dust my wets? SERVER: you can just ask for parmesan cheese ME: *confused lifting all of my spaghetti with my hands* please. My wets.",
                      user: "@horsedivorce",
                      date: "04-05-2019"
                  },
                  {
                      content: "BUILDING INSPECTOR: Whats this called? DARTH VADER: The death- [inspectors eyes look up from his clipboard] DARTH VADER: Uh, the health star.",
                      user: "@bobvulfov",
                      date: "10-14-2015"
                  }
                ]
            }
        },
        methods: {
            isActive() {
                //toggles the button state to be the opposite of its current state. 
                this.btnState = !this.btnState;
            }
        }  
    }
</script>

<style scoped>
    #mainContainer {
        width: 100vw;
        padding-top: 2vh;
    }

    #toggleContainer {
        margin-right: 70vw;
        height: 5vh;
        padding-bottom: 3vh;
        display: grid;
        align-items: center;
    }

    /*Toggle button style*/

    #toggleBtn {
        display: none;
    }

    #theToggle {
        cursor: pointer;
        background-color: rgb(14, 91, 158);
        color: white;
        font-weight: bold;
        padding: 1.5vh 1vw 1.2vh 1vw;
        margin-left: 3vw;
        width: 15vw;
        text-align: center;
        border-radius: 15px;
        box-shadow: 2px 2px rgb(105, 159, 230);
        user-select: none;
    }

    #theToggle:active {
        background-color: rgb(11, 68, 117);
    }

    /*a set class for the caintainer card view*/
    .postContainerCard {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }

    /*Below is the list view CSS*/

    .listViewContainer {
        width: 90vw;
        height: 10vh;
        background-color:rgb(191, 218, 241);
        display: grid;
        grid-template-columns: repeat(2, minmax(0, 1fr));
        grid-template-rows: 2;
        justify-items: start;
        align-items: center;
        margin-bottom: 1vh;
        margin-left: 1vw;
        border-radius: 15px;
        padding: 10px 10px 10px 10px;
    }
    .listViewContent {
        margin-left: 2vw;
        grid-column: 1 / 3;
        grid-row: 1;
        text-align: start;
    }
    .listViewUser {
        grid-column: 1;
        grid-row: 2;
        margin-left: 4vw;
    }
    .listViewDate {
        grid-column: 2;
        grid-row: 2;
        align-self: end;
        justify-self: end;
    }

    /*Below is the card view CSS*/

    .cardViewContainer {
        width: 30vw;
        height: 35vh;
        background-color:rgb(191, 218, 241);
        display: grid;
        grid-template-columns: repeat(2, minmax(0, 1fr));
        grid-template-rows: 2;
        justify-items: start;
        align-items: center;
        margin-bottom: 1vh;
        margin-left: 1vw;
        border-radius: 30px;
        padding: 10px 10px 10px 10px;
    }
    .cardViewContent {
        margin-left: 2vw;
        grid-column: 1 / 3;
        grid-row: 1;
        text-align: start;
    }
    .cardViewUser {
        grid-column: 2;
        grid-row: 2;
        margin-left: 4vw;
    }
    .cardViewDate {
        grid-column: 2;
        grid-row: 2;
        align-self: end;
        justify-self: end;
        margin-right: 1vw;
    }
</style>