<template>
  <div class="content">
    <div class="body-content">
      <v-stepper v-model="e1">
        <v-stepper-header>
          <v-stepper-step :complete="e1 > 1" step="1" color="success">
            Information
          </v-stepper-step>

          <v-divider></v-divider>

          <v-stepper-step :complete="e1 > 2" step="2" color="success">
            Payment Details
          </v-stepper-step>

          <v-divider></v-divider>

          <!-- <v-stepper-step step="3">
            Name of step 3
          </v-stepper-step> -->
        </v-stepper-header>

        <v-stepper-items>
          <v-stepper-content step="1">
            <div class="mb-4">
              <div class="block-content">
                <div class="box-content">
                  <div class="detail-pay">
                    <div class="header-pay">
                      <div class="box1-header-l">
                        <div class="b1-hl-title">My Ticket</div>
                        <div class="b1-hl-logo"><img src="/ticket.png" /></div>
                      </div>
                    </div>
                  </div>
                  <div class="card-ticket">
                    <div class="box-ticket">
                      <div class="title-ticket">name of concert lorem ipsum industry</div>
                      <div class="date-ticket">
                        <div class="icon-date"><img src="/calendar_b.png" /></div>
                        <div class="detail-date">Mon Sep 8, 2023</div>
                      </div>
                      <div class="time-ticket">
                        <div class="icon-time"><img src="/clock_b.png" /></div>
                        <div class="detail-time">06:00 PM - 09:00 PM</div>
                      </div>
                      <div class="location-ticket">
                        <div class="icon-location"><img src="/location_b.png" /></div>
                        <div class="detail-location">Location : Thunder Dome Muang Thong Thani</div>
                      </div>
                      <div class="price-ticket">
                        <div class="icon-price"><img src="/bath_b.png" /></div>
                        <div class="detail-price">{{ price }} bath</div>
                      </div>
                      <div class="-solid"></div>
                      <div class="add-ticket">
                        <div class="del-ticket" @click="delTicket()">
                          <img src="/minus.png" />
                        </div>
                        <div class="status-ticket">{{ ticket }}</div>
                        <div class="plus-ticket" @click="addTicket()">
                          <img src="/plus.png" />
                        </div>
                      </div>
                    </div>
                    <div class="img-tiket">
                      <div class="img-item"><img src="/concert.jpg" /></div>
                    </div>
                  </div>
                </div>
                <div class="box-content">
                  <div class="detail-pay">
                    <div class="header-pay">
                      <div class="box1-header-l">
                        <div class="b1-hl-title">Delivery</div>
                        <div class="b1-hl-logo"><img src="/fast-delivery.png" /></div>
                      </div>
                    </div>
                    <div class="header-title">Mobile Entry - Free</div>
                    <div class="inner-item">
                      Tickets Available by {{ date_ticket }}<br>
                      These mobile tickets will be transferred directly to you from a trusted seller. We'll email <br>
                      you instructions on how to accept them on hte original ticket provider's mobille app.
                    </div>
                    <!-- <div class="-solid"></div> -->
                  </div>
                </div>
              </div>
            </div>

            <div class="btn-next">
              <v-btn color="success" @click="nextPage() & totalFee() & sumTotal() & sumAllPrice()">
                Continue
              </v-btn>
            </div>
          </v-stepper-content>

          <v-stepper-content step="2">
            <div class="mb-4">
              <div class="block-content-pay">
                <div class="box-content-pay">
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
                    <div class="block-credit">
                      <div class="box-credit">
                        <div class="title-credit">
                          <v-radio-group v-model="radios">
                            <v-radio class="check-card" value="radios_active" color="success"></v-radio>
                          </v-radio-group>
                          <div>Credit Card</div>
                        </div>
                        <div class="logo-credit">
                          <div><img src="/credit_cards.png" /></div>
                        </div>
                      </div>
                      <div class="detail-credit">
                        Safe money transfer using your bank account. <br>
                        Visa, maestro, discover, american express.
                      </div>
                    </div>
                    <div class="-solid"></div>
                    <div class="input-card">
                      <div class="name-card">
                        <div class="title-name-card">
                          name on a card
                        </div>
                        <div class="box-name-card">
                          <v-text-field v-model="card_name" placeholder="NAME ON A CARD" outlined>
                          </v-text-field>
                        </div>
                      </div>
                      <div class="number-card">
                        <div class="title-number-card">
                          card number
                        </div>
                        <div class="box-number-card">
                          <v-text-field v-model="card_number" placeholder="CARD NUMBER" :counter="16" :maxlength="16" outlined>
                          </v-text-field>
                        </div>
                      </div>
                      <div class="options-card">
                        <div class="cvv-card mr-2">
                          <div class="title-cvv-card">cvv code</div>
                          <div class="input-cvv-card">
                            <v-text-field v-model="cvv" placeholder="CVV" :counter="3" :maxlength="3" outlined>
                            </v-text-field>
                          </div>
                        </div>
                        <div class="exp-card ml-2">
                          <div class="title-exp-card">expiry date</div>
                          <div class="input-exp-card">
                            <v-text-field v-model="exp" v-on:input="qa" placeholder="MM/YY" maxlength='5' outlined>
                            </v-text-field>
                          </div>

                        </div>
                      </div>
                    </div>
                    <!-- <div class="-solid"></div>
                    <div class="or-pay-title">Or Pay With</div>
                    <div class="or-pay">By using a digital wallet and continuing past this page,you have read and are acceptin the
                      <span>Terms of User.</span>
                    </div> -->
                  </div>
                </div>
                <div class="box-content-pay">
                  <div class="detail-pay">
                    <div class="header-pay">
                      <div class="box1-header-l">
                        <div class="b1-hl-title">Total</div>
                      </div>
                      <div class="box1-header-r">
                        <div class="sum-total">{{ all_price }} ฿</div>
                      </div>
                    </div>
                    <div class="header-title-total">Tickets</div>
                    <div class="item-total">
                      <div class="detail-total">Resale Tickets : {{ price }} x {{ ticket }}</div>
                      <div class="number-total">{{ sum_ticket }} ฿</div>
                    </div>
                    <div class="header-title-total">Notes From Seller</div>
                    <div class="list-total">
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit.
                      Sequi sed aliquam voluptatibus! Quam consequuntur vel cum unde veniam labore
                      et commodi ducimus harum totam explicabo placeat, optio,
                      quisquam, repellendus impedit.
                    </div>
                    <div class="header-title-total">Fees</div>
                    <div class="item-total">
                      <div class="detail-total">Service Fee : {{ fee }} x {{ ticket }}</div>
                      <div class="number-total">{{ sum_fee }} ฿</div>
                    </div>
                    <div class="item-total">
                      <div class="detail-total">Order Processing Fee</div>
                      <div class="number-total">{{ order_fee }} ฿</div>
                    </div>
                    <div class="header-title-total">Delivery</div>
                    <div class="item-total">
                      <div class="detail-total">Mobile Entry</div>
                      <div class="number-total">Free</div>
                    </div>
                    <div class="header-title-total -ven">*All Sales Final - No Refunds</div>
                    <div class="box-accep">
                      <div class="check-accep">
                        <v-checkbox v-model="enabled" value="">
                        </v-checkbox>
                      </div>
                      <div class="text-accep">I have read and agree to the current <span>Terms of Use.</span></div>
                    </div>
                    <v-btn class="btn-submit" :disabled="!enabled" @click="submitPage()">
                      Place Order
                    </v-btn>
                    <div class="text-sp-order">*Exceptions may apply, see our Terms of Use.</div>
                  </div>
                </div>
              </div>
            </div>
            <div class="btn-back">
              <v-btn color="success" @click="e1 = 1">
                Back
              </v-btn>              
            </div>
          </v-stepper-content>

          <!-- <v-stepper-content step="3">
            <v-card class="mb-12" color="grey lighten-1" height="200px"></v-card>

            <v-btn color="primary" @click="e1 = 1">
              Continue
            </v-btn>

            <v-btn text>
              Cancel
            </v-btn>
          </v-stepper-content> -->
        </v-stepper-items>
      </v-stepper>
    </div>
  </div>
</template>

<script>
import Swal from "sweetalert2/dist/sweetalert2.js";

export default {
  name: 'IndexPage',
  data: () => ({
    dateValue: null,
    e1: 1,
    date_ticket: "Mon Sep 8, 2023",
    radios: "radios_active",
    selected: "",
    total: 1000,
    sum_total: "",
    sum_ticket: "",
    price: 1000,
    ticket: 1,
    total_ticket: 1,
    all_price: "",
    fee: 10,
    sum_fee: "",
    order_fee: 5,
    namecard: "",
    finalVal: "",
    card_name: "",
    card_number: "",
    cvv: "",
    exp: "",
    test: "",
    test1: "test",
    enabled: false,
  }),

  mounted() {

  },

  methods: {
    nextPage() {
      this.e1++;
    },
    nextPage1() {
      this.e1 = 1;
    },
    addTicket() {
      this.ticket += 1;
    },
    delTicket() {
      if (this.ticket <= 1) {
        this.ticket = 1;
      }
      else {
        this.ticket -= 1;
      }
    },
    totalFee() {
      this.sum_fee = this.fee * this.ticket;
    },
    sumTotal() {
      this.sum_ticket = this.price * this.ticket;
    },
    sumAllPrice() {
      this.all_price = this.sum_fee + this.sum_ticket + this.order_fee;
    },
    qa() {
      this.exp = this.exp.replace(
        /^([1-9]\/|[2-9])$/g, '0$1/'
      ).replace(
        /^(0[1-9]|1[0-2])$/g, '$1/'
      ).replace(
        /^([0-1])([3-9])$/g, '0$1/$2'
      ).replace(
        /^(0?[1-9]|1[0-2])([0-9]{2})$/g, '$1/$2'
      ).replace(
        /^([0]+)\/|[0]+$/g, '0'
      );
      return this.exp;
    },
    submitPage() {
      Swal.fire({
        position: 'center',
        icon: 'success',
        title: 'Your Success',
        showConfirmButton: false,
        timer: 2500
      })
      this.sum_fee = 10;
      this.sum_ticket = 1000;
      this.all_price = 1015;
      this.card_name = "";
      this.card_number = "";
      this.cvv = "";
      this.exp = "";
      this.ticket = 1;
      this.e1 = 1;
      this.enabled = false;
    }
  },

};
</script>
