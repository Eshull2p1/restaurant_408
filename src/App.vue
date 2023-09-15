<script setup>
import { ref } from "vue";

const travelList = ref([
  {
    Name: "สุนทรารมณ์",
    price: 219,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://scontent.fbkk3-5.fna.fbcdn.net/v/t39.30808-6/275785111_104666465518677_1157293760977336208_n.jpg?_nc_cat=111&ccb=1-7&_nc_sid=a2f6c7&_nc_eui2=AeGfOBCX2uU4HXosa58T46NDmqAF2dZmucuaoAXZ1ma5y9kH8BDaezbGoo4UntP1oBBLjFS8hMdiSqGxUYFF5qrv&_nc_ohc=EglJ2SY01kIAX9BrOjK&_nc_zt=23&_nc_ht=scontent.fbkk3-5.fna&oh=00_AfAydXW_HaoG1jycNbPvzX_vVo3DddR_Uu4YPC2X62TcsQ&oe=6507C5D3 ",
  },
  {
    Name: "ฯลฯ",
    price: 199,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://scontent.fbkk3-3.fna.fbcdn.net/v/t39.30808-6/326435697_501993212005268_2267045348590722770_n.jpg?_nc_cat=103&ccb=1-7&_nc_sid=a2f6c7&_nc_eui2=AeH6wOSgjmnBu0mx2CdHF44GxTbvRg4F5HPFNu9GDgXkc69Xy8MF7kytaavwQfgDD0pujV73nQ0rtrM3iipacngf&_nc_ohc=lq-ZZCnaPS4AX-Aj8Pk&_nc_zt=23&_nc_ht=scontent.fbkk3-3.fna&oh=00_AfCTul08WJdjjfITVF6O7gMeqHBEGGpM3Krhf0auP4CTdQ&oe=6508A1CF",
  },
  {
    Name: "Tamma Cafe",
    price: 500,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://scontent.fbkk4-2.fna.fbcdn.net/v/t39.30808-6/361305041_779199773993037_7111305937619716444_n.jpg?_nc_cat=110&ccb=1-7&_nc_sid=a2f6c7&_nc_eui2=AeE8AmCqgV6vH2N-XXd2RtluKhovrXyAa8YqGi-tfIBrxtoycFMAaCWmeArKq2l-FXQVlFi6wW5SrIh2WO-he8vv&_nc_ohc=VqKbsOGLFokAX8DCKgu&_nc_zt=23&_nc_ht=scontent.fbkk4-2.fna&oh=00_AfCt0Gg-_-Ia_UW_05Bi1kyqBh9zhtQZUgKmzYJeXiroFA&oe=6508E387",
  },
  {
    Name: "OverNight",
    price: 299,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://scontent.fbkk4-1.fna.fbcdn.net/v/t39.30808-6/314943429_107842845474701_641691726405226769_n.jpg?stp=cp6_dst-jpg&_nc_cat=107&ccb=1-7&_nc_sid=a2f6c7&_nc_eui2=AeE2jtbOWcxEQxWt5VOcktcwEYxzLzXtdwsRjHMvNe13CzOH8qAa3eRI-d2PHcleZmuOx09IYZ10rhrdDC906sgc&_nc_ohc=DyHXRvzCagcAX_fribh&_nc_zt=23&_nc_ht=scontent.fbkk4-1.fna&oh=00_AfAoL4Zm7y1uFB0hgQ12PrSn3_McQvhmgjIM1GvGlBxpIQ&oe=6507B9F1",
  },
  {
    Name: "ChaChaBBT",
    price: 150,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://scontent.fbkk4-1.fna.fbcdn.net/v/t39.30808-6/305497489_511848984083670_6337765249920522806_n.jpg?_nc_cat=107&ccb=1-7&_nc_sid=a2f6c7&_nc_eui2=AeHQ2zpPuBNt8XKKP0Zzy37dkN9S5DAjly2Q31LkMCOXLXNAtHXMlwrMFes6rpDOq0TvyPgTt3vsfSOdiRtzMGyA&_nc_ohc=-d1v9V8NGoYAX9i1hAJ&_nc_zt=23&_nc_ht=scontent.fbkk4-1.fna&oh=00_AfBMvWy0d3WHgvuH15RFAGeuo2jLdUv9PjzDXdQJsljhGQ&oe=6508C09C",
  },
  {
    Name: "ในใจเทอ",
    price: 0,
    count_tb: 0,
    date: "",
    customer: "",
    Tel: "",
    img: "https://cdn.discordapp.com/attachments/989851222959874111/1151946513635889193/image.png",
  },
]);

const booking = ref([]);

function table_controll(Name, count_tb, date, customer, Tel) {
  if (count_tb > 0 && date !== "" && customer !== "" && Tel !== "") {
    const box = {
      Name: Name,
      count_tb: count_tb,
      price: count_tb * travelList.value.find((box) => box.Name === Name).price,
      date: date,
      customer: customer,
      Tel: Tel,
    };
    booking.value.push(box);
  }
}

function cancle(index) {
  booking.value.splice(index, 1);
}
</script>

<template>
  <h1 class="title">จองร้านอาหาร</h1>
  <div class="card_body">
    <p>***กรุณากรอกข้อมูลให้ครบก่อนกดยืนยันการจอง***</p>
    <div class="ColShop">
      <div class="col" v-for="(i, index) in travelList" :key="index">
        <div class="card" style="width: 18rem">
          <img :src="i.img" class="card-img-top" />
          <div class="card-body">
            <h5 class="card-title">{{ i.Name }}</h5>
            <p>ราคา : {{ i.price }}</p>
            <p v-if="i.price === 0">ให้เพื่อนเลี้ยง</p>
            <p v-if="i.price !== 0">ᅟ</p>
            <div class="date_row">
              วันที่
              <input type="date" class="boxDate" v-model="i.date" required />
            </div>
            <div class="input_box">
              ผู้จอง
              <input
                type="text"
                class="form-control"
                placeholder="ชื่อ-สกุล"
                v-model="i.customer"
                required
              />
            </div>
            <div class="input_box">
              <label class="form-label"> เบอร์</label>
              <div class="input-group">
                <input
                  type="text"
                  class="form-control"
                  v-model="i.Tel"
                  placeholder="โปรดใส่เบอร์ที่ติดต่อได้"
                  required
                  maxlength="10"
                />
              </div>
            </div>
            <div>
              <P>จำนวน</P>
              <input
                type="number"
                class="boxCount"
                v-model="i.count_tb"
                required
              />
            </div>
            <a
              class="btn btn-success"
              @click="
                table_controll(i.Name, i.count_tb, i.date, i.customer, i.Tel)
              "
              >จอง</a
            >
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="table_total" v-if="booking.length > 0">
    <table class="table" v-if="booking.length > 0">
      <thead>
        <tr>
          <th scope="col" class=""></th>
          <th scope="col">ร้าน</th>
          <th scope="col">จำนวน</th>
          <th scope="col">ราคา</th>
          <th scope="col">วันที่</th>
          <th scope="col">ผู้จอง</th>
          <th scope="col">เบอร์</th>
          <th scope="col"></th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(i, index) in booking" :key="index">
          <th scope="row">{{ index + 1 }}</th>
          <td>{{ i.Name }}</td>
          <td>{{ i.count_tb }}</td>
          <td>{{ i.price }}</td>
          <td>{{ i.date }}</td>
          <td>{{ i.customer }}</td>
          <td>{{ i.Tel }}</td>
          <td>
            <button
              type="button"
              class="btn btn-outline-danger"
              @click="cancle(index)"
            >
              ยกเลิก
            </button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.ColShop {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  justify-items: stretch;
  align-items: stretch;
  column-gap: 50px;
  row-gap: 20px;
  background-color: #4e8c9b;
  padding: 30px;
}

.date_row {
  max-width: 180px;
  border-radius: 5px;
  background-color: rgb(8, 8, 0);
  color: white;
  padding-left: 3px;
}

.boxDate {
  padding: 3px;
}
.boxCount {
  background-color: aliceblue;
  color: black;
  border-radius: 5px;
  box-shadow: 0px 0px 0px 1px rgba(0, 0, 0, 0.87);
  margin-bottom: 10px;
}

.title {
  background-color: #fff1fc;
  padding: 20px;
  margin-bottom: 30px;
  border: 10px double #916386;
  border-radius: 20px;
  box-shadow: 0px 0px 16px 6px rgb(249, 67, 255);
}
.card_body {
  background-color: rgb(246, 250, 253);
  padding: 20px;
  border-radius: 20px;
  margin-top: 20px;
  box-shadow: 0px 0px 16px 2px #00e9ff;
}

.table_total {
  background-color: white;
  margin-top: 20px;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0px 0px 16px 1px rgb(249, 67, 255);
}
.input_box {
  font-weight: 600;
  margin-top: 5px;
}
</style>
