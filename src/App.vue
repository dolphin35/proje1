<template>
  <div>
    <Header></Header>
    <carousel items="1" mergeFit loop class="bg-success">
      <div style="height: 500px">
        asd
      </div>
    </carousel>
    <b-container>
      <carousel items="4" loop :margin="10" class="mt-5" autoplay :responsive="responsive">
        <b-card v-for="(value, key) in urunler" :key="'obj -' + key" border-variant="0"
                body-class="text-left" no-body style="height: 400px;">
          <b-card-body>
            <div class="overflow-hidden">
              <b-card-img class="object-fit-contain img-hover" :src="value.image" top height="200"></b-card-img>
            </div>
            <p class="text-truncate-body" :title="value.text"><b>{{ value.title }}</b> {{ value.text }}</p>
          </b-card-body>
          <b-card-footer footer-border-variant="0" footer-bg-variant="dark" footer-text-variant="light">
            <p class="card-text">
              <small>
                <del class="font-weight-bold text-danger"> {{ value.delPrice }} ₺</del>
              </small>
              <strong class="float-right">{{ value.price }} ₺</strong></p>
          </b-card-footer>
        </b-card>

      </carousel>

      <carousel items="4" loop :margin="10" class="mt-5" autoplay :responsive="responsive">
        <b-card v-for="(value, key) in urunler" :key="'obj -' + key" border-variant="0"
                body-class="text-left" no-body style="height: 400px;">
          <b-card-body>
            <div class="overflow-hidden">
              <b-card-img class="object-fit-contain img-hover" :src="value.image" top height="200"></b-card-img>
            </div>
            <p class="text-truncate-body" :title="value.text"><b>{{ value.title }}</b> {{ value.text }}</p>
          </b-card-body>
          <b-card-footer footer-border-variant="0" footer-bg-variant="dark" footer-text-variant="light">
            <p class="card-text">
              <small>
                <del class="font-weight-bold text-danger"> {{ value.delPrice }} ₺</del>
              </small>
              <strong class="float-right">{{ value.price }} ₺</strong></p>
          </b-card-footer>
        </b-card>
      </carousel>

    </b-container>

  </div>
</template>

<script>


import Header from "@/Header";
import carousel from 'vue-owl-carousel'

export default {
  name: 'App',
  components: {Header, carousel},
  data() {
    return {
      urunler: [
        {
          title: 'LENOVO',
          text: 'Ideapad Intel Celeron N4020 4gb 128gb Ssd Freedos 14" Hd Taşınabilir Bilgisayar 81vu006stx',
          image: 'https://cdn.dsmcdn.com//ty57/product/media/images/20210119/15/55214906/131969474/0/0_org.jpg',
          price: 5000,
          delPrice: 9000,
        },
        {
          title: 'Monster',
          text: 'Tulpar T7 V20.3 Intel Core I7 10750h 16gb 512gb Ssd Rtx3060 Max-p Freedos 17.3',
          image: 'https://cdn.dsmcdn.com//ty38/product/media/images/20201225/17/42098874/123203036/1/1_org.jpg',
          price: 4000,
          delPrice: 5000,
        },
        {
          title: 'Dell',
          text: 'V15-ııl I3 1005g1 12gb 512g Ssd Dos 15.6 Fhd 82c500jftxz11 82C500JFTXZ11',
          image: 'https://cdn.dsmcdn.com//ty68/product/media/images/20210214/22/62463462/140376449/1/1_org.jpg',
          price: 6000,
          delPrice: 8000,
        },
        {
          title: 'Casper',
          text: 'Casper G315 4b750d2f161c I7-10750h 16gb 1tb Hdd 256gb Ssd 4gb Gtx1650ti 15.6 Fhd Linux',
          image: 'https://cdn.dsmcdn.com//ty13/product/media/images/20201006/10/13666729/85488745/1/1_org.jpg',
          price: 6000,
          delPrice: 7000,
        },
      ],
      loading: true,
      responsive: {
        0: {
          items: 1
        },
        600:{
          items:3
        },
        960:{
          items:3
        },
        1200:{
          items:4
        }
      }
    }
  },
  created() {
    window.$bvModal = this.$bvModal;
  }
}

</script>

<style lang="scss">
body {
  background: #eaeaea;
}

.text-truncate-body {
  display: -webkit-box !important;
  overflow: hidden;
  word-break: break-word;
  text-overflow: ellipsis;
  -webkit-line-clamp: 4;
  -webkit-box-orient: vertical;
}

.list-item {
  display: inline-block;
}

.list-enter-active, .list-leave-active {
  transition: all 1s;
}

.list-enter /* .list-leave-active below version 2.1.8 */
{
  opacity: 0;
  transform: translateY(30px);
}

.list-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}

.img-hover {
  transition: all 500ms;

  &:hover {
    transform: scale(1.2);

  }
}

.object-fit-cover {
  object-fit: cover;
  object-position: center;

}

.object-fit-contain {
  object-fit: contain;
  object-position: center;
}

</style>
