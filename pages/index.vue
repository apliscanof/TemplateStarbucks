<template>
  <v-continer fluid >
    <v-row>
      <v-col cols="12" class="pa-0">
        <v-card height="500" color="#d4e9e2" flat rounded="0">
          <v-container fluid class="fill-height">
            <v-row justify="start" align="center">
              <v-col cols="12" sm="5">
                <v-card-title 
                  class="text-h3" 
                  style="font-size: 35px !important; line-height: 75px; font-weight: 400;">FREE COFFEE IS A TAP AWAY
                </v-card-title>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-col>
    </v-row>
    <v-row class="mx-5">
      <v-container>
        <v-row justify="center">
          <v-col cols="6" class="text-center black--text">
            <h5 class="font-weight-bold text-h5">Getting started is easy</h5>
            <p>Earn Stars and get rewarded in a few easy steps.</p>
          </v-col>
        </v-row>
        <v-row>
          <v-col v-for="(item,i) in cards" :key="i" cols="12" md="4" class="pa-0" >
            <v-card flat>
              <v-container>
                <v-row>
                  <v-col cols="12" class="text-center black--text">
                    <v-icon color="#008248" size="40">{{ item.icon }}</v-icon>
                    <h2><strong>{{ item.title }}</strong></h2>
                    <p>{{ item.description }}</p>
                  </v-col>
                </v-row>
              </v-container>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-row>
    
    <v-card color="#f1f8f6" rounded="0" flat>
      <v-card-title class="text-center justify-center py-8">
        <h5 class="font-weight-bold text-h5 black--text">
          Get your favorites for free
        </h5>
      </v-card-title>

      <v-tabs
        v-model="tab"
        background-color="transparent"
        color="#000000" centered
      >
      <v-tabs-slider color="#008248"></v-tabs-slider>
        <v-tab
          v-for="item in items"
          :key="item.tab"
        >
          <h2 >{{ item.tab }}</h2><v-icon color="#CD853F" small>mdi-star</v-icon>
        </v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab" justify="center" align="center">
        <v-tab-item
          v-for="item in items" :key="item.tab">
          <v-card color="#d4e9e2" rounded="0">
            <v-container>
              <v-row>
                <v-col cols="12" md="6" :class="`${d-flex}`">
                  <v-img :src="item.imgScr" max-width="375" class=""></v-img>
                </v-col>
                <v-col cols="12" md="6" class="text-start align-center">
                  <h3 style="font-size: 25px !important; line-height: 50px !important; font-weight: 400; color: #000000;">{{ item.title }}</h3>
                  <p class="font-weight-regular mt-5" style="font-size: 1rem !important; line-height: 25px;">{{ item.description }}</p>
                </v-col>
              </v-row>
            </v-container> 
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>

    <v-row>
      <v-container>
        <v-row justify="center">
          <v-col cols="6" class="text-center black--text">
            <h5 class="font-weight-bold text-h5">Endless Extras</h5>
            <p>Joining Starbucks® Rewards means unlocking access to exclusive benefits. Say hello to easy ordering, tasty Rewards and—yes, free coffee.</p>
          </v-col>
        </v-row>
        <v-row>
          <v-col v-for="(item,i) in card" :key="i" cols="12" md="4" class="pa-0" >
            <v-card flat>
              <v-container>
                <v-row>
                  <v-row justify="center">
                    <v-img max-width="85" :src="item.src"></v-img>
                  </v-row>
                  <v-col cols="12"  class="text-center black--text">
                    <h2><strong>{{ item.title }}</strong></h2>
                    <p>{{ item.description }}</p>
                  </v-col>
                  <v-row justify="center">
                    <v-btn plain color="#008248">Learn More</v-btn>
                  </v-row>
                </v-row>  
              </v-container>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-row>

    <v-card color="#f3f1e7" rounded="0">
      <v-row>
        <v-container>
          <v-row justify="center">
            <v-col cols="6" class="text-center">
              <h5 class="font-weight-bold text-h5">Cash or card, you earn Stars</h5>
              <p>No matter how you pay, you can earn Stars with your morning coffee. Those Stars add up to (really delicious) Rewards.</p>
            </v-col>
          </v-row>
        </v-container>
      </v-row>
    </v-card>
  </v-continer>
</template>

<script>
export default {
  data()  {return {
    cards:[
      {
      icon: 'mdi-numeric-1-circle-outline',
      title: 'Create an account',
      description: 'To get started, join now. You can also join in the app to get access to the full range of Starbucks® Rewards benefits.',
    },
    {
      icon: 'mdi-numeric-2-circle-outline',
      title: 'Order and pay how you’d like',
      description: 'Use cash, credit/debit card or save some time and pay right through the app. You’ll collect Stars all ways. Learn how',
    },
    {
      icon: 'mdi-numeric-3-circle-outline',
      title: 'Earn Stars, get Rewards',
      description: 'As you earn Stars, you can redeem them for Rewards—like free food, drinks, and more. Start redeeming with as little as 25 Stars!',
    }
  ],
  tab: null,
        items: [
          {tab: '25', title:'Customize your drink', description:'Make your drink just right with an extra espresso shot, nondairy milk or a dash of your favorite syrup.', imgScr: 'https://www.starbucks.com/weblx/images/rewards/reward-tiers/025.png' },
          {tab: '100', title:'Brewed hot or iced coffee or tea, bakery item, packaged snack and more', description:'Treat yourself to an iced coffee, buttery croissant, bag of chips and more.', imgScr:'https://www.starbucks.com/weblx/images/rewards/reward-tiers/100.png'}, 
          {tab: '200', title:'Handcrafted drink (Cold Brew, lattes and more) or hot breakfast', description:'Turn good mornings great with a delicious handcrafted drink of your choice, breakfast sandwich or oatmeal on us.', imgScr:'https://www.starbucks.com/weblx/images/rewards/reward-tiers/200.png' }, 
          {tab: '300', title:'Sandwich, protein box or at-home coffee', description:'Enjoy a PM pick-me-up with a lunch sandwich, protein box or a bag of coffee—including Starbucks VIA Instant®.', imgScr:'https://www.starbucks.com/weblx/images/rewards/reward-tiers/300.png'},
          {tab: '400', title:'Select Starbucks® merchandise', description:'Take home a signature cup, drink tumbler or your choice of coffee merch up to $20.', imgScr:'https://www.starbucks.com/weblx/images/rewards/reward-tiers/400.png'} 
        ],
  card:[
    { 
      src:'https://www.starbucks.com/weblx/images/rewards/benefits/1-fun-freebies.jpg',
      title:'Fun freebies',
      description:'Not only can you earn free coffee, look forward to a birthday treat plus coffee and tea refills.'
    },
    {
      src:'https://www.starbucks.com/weblx/images/rewards/benefits/2-order-and-pay-ahead.jpg',
      title:'Order & pay ahead',
      description:'Enjoy the convenience of in-store, curbside or drive-thru pickup at select stores.',
    },
    {
      src:'https://www.starbucks.com/weblx/images/rewards/benefits/3-get-to-free-faster.jpg',
      title:'Get to free faster',
      description:'Earn Stars even quicker with Bonus Star challenges, Double Star Days and exciting games.',
    } 
  ]
      }
  }}

</script>
