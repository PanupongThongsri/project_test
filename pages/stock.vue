<template>
    <div class="content">
      <div class="block-content">
        <div class="box1">
          <div class="select-item">
            <h2 class="mb-4">Select to show</h2>
            <v-row>
              <v-col class="d-flex" cols="12" sm="6">
                fewrfwe
                <v-select :items="items" label="Outlined style" outlined></v-select>
              </v-col>
              <v-col class="d-flex" cols="12" sm="6">
                <div>fkemfker</div>
                <v-select :items="items" label="Outlined style" outlined></v-select>
              </v-col>            
            </v-row>
          </div>
          <div class="detail-pay">
            <div class="header-pay">
              <div class="box1-header-l">
                <div class="b1-hl-title">Payment</div>
                <div class="b1-hl-logo"><img src="/check-mark.png" /></div>
              </div>
              <div class="box1-header-r">
                <div class="box1-header-r">
                  <div class="b1-hr-title">
                    <span>offical card of</span>ticketmaster
                  </div>
                  <div class="b1-hr-logo"><img src="/credit-card.png" /></div>                
                </div>
              </div>
            </div>
            <div class="header-title">Select To Payment</div>
            <div class="-solid"></div>
            <div class="header-title">Or Pay With</div>
          </div>
        </div>
        <div class="box2">
          <div class="list-status">
            <div class="d-flex">
              <h2>Total</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'IndexPage',
    data: () => ({
      items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
    }),
  }
  </script>
  