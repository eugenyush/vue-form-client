<template>
    <div class="container">
    <div class="headr">
      Форма создания клиента
    </div>  
     <form @submit.prevent="onSubmit">
          <div class="form-main">
                <div class="title">Личные данные</div>
             <div class="form-atr first-atr">
                <p>
                    <label for="name">Имя<span class="fillin">*</span></label>
                    <input id="name" v-model="form.name" placeholder="Введите имя">
                    <span v-if="$v.form.name.$dirty && !$v.form.name.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                <p>
                    <label for="surname">Фамилия<span class="fillin">*</span></label>
                    <input id="surname" v-model="form.surname" placeholder="Введите фамилию">
                    <span v-if="$v.form.surname.$dirty && !$v.form.surname.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                 <p>
                    <label for="patronymic">Отчество</label>
                    <input id="patronymic" v-model="form.patronymic" placeholder="Введите отчество" >
                </p>
                 <p>
                    <label for="datebirth">Дата рождения<span class="fillin">*</span></label>
                    <input type="date" id="datebith" v-model="form.datebirth" placeholder="Введите дату рождения">
                    <span v-if="$v.form.datebirth.$dirty && !$v.form.datebirth.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                 <p>
                    <label for="phon">Номер телефона<span class="fillin">*</span></label>
                    <input id="phon" v-model="form.phon" placeholder="+7">
                    <span v-if="$v.form.phon.$dirty && !$v.form.phon.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                    <span v-if="$v.form.phon.$dirty && !$v.form.phon.alphaNum"  class="invalid-feedback">Номер не верный</span>
                </p>
                 <p class="flex-row">
                    <label for="paul">Пол:</label>
                    <input type="radio" value="Мужчина" v-model="form.paul">
                    <label>Муж.</label>
                    <input type="radio" value="Женщина" v-model="form.paul">
                    <label>Жен.</label>
                </p>
                 <p>
                    <label for="custgroup">Группа клиентов<span class="fillin">*</span></label>
                    <select multiple size="3" id="custgroup" v-model="form.custgroup">
                        <option value="VIP">VIP</option>
                        <option value="Проблемные">Проблемные</option>
                        <option value="ОМС">ОМС</option>
                    </select>
                    <span v-if="$v.form.custgroup.$dirty && !$v.form.custgroup.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                   <p>
                    <label for="physician">Лечащий врач</label>
                    <select id="physician" v-model="form.physician">
                        <option value="Иванов">Иванов</option>
                        <option value="Захаров">Захаров</option>
                        <option value="Чернышева">Чернышева</option>
                    </select>
                </p>
                 <p class="flex-row">
                    <label for="checkbox" >Не отправлять СМС:</label>
                    <input type="checkbox" v-model = "form.checkbtn">
                </p>
            </div>
            <div class="title">Адрес</div>
            <div class="form-atr address-atr">
                <p>
                    <label for="zipcode">Индекс</label>
                    <input id="zipcode" v-model="form.zipcode" placeholder="Введите индекс">
                </p>
                <p>
                    <label for="country">Страна</label>
                    <input id="country" v-model="form.country" placeholder="Введите страну">
                </p>
                <p>
                    <label for="area">Область</label>
                    <input id="area" v-model="form.area" placeholder="Введите область">
                </p>
                <p>
                    <label for="city">Город<span class="fillin">*</span></label>
                    <input id="city" v-model="form.city" placeholder="Введите город">
                    <span v-if="$v.form.city.$dirty && !$v.form.city.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                <p>
                    <label for="street">Улица</label>
                    <input id="street" v-model="form.street" placeholder="Введите улицу">
                </p>
                <p>
                    <label for="house">Дом</label>
                    <input id="house" v-model="form.house" placeholder="Введите дом">
                </p>
            </div>
            <div class="title">Документ</div>
            <div class="form-atr passport-atr">
                <p>
                    <label for="doctype">Тип документа<span class="fillin">*</span></label>
                    <select id="doctype" v-model="form.doctype">
                        <option value="Паспорт">Паспорт</option>
                        <option value="Свидетельство о рождении">Свидетельство о рождении</option>
                        <option value="Вододительское удостоверение">Вододительское удостоверение</option>
                    </select>
                    <span v-if="$v.form.doctype.$dirty && !$v.form.doctype.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                <p>
                    <label for="series">Серия документа</label>
                    <input id="series" v-model="form.series" placeholder="Введите серию">
                </p>
                <p>
                    <label for="number">Номер документа</label>
                    <input id="number" v-model="form.number" placeholder="Введите номер">
                </p>
                <p>
                    <label for="iswhom">Кем выдан</label>
                    <input id="iswhom" v-model="form.iswhom" placeholder="Введите кем выдан">
                </p>
                <p>
                    <label for="dateissue">Дата выдачи<span class="fillin">*</span></label>
                    <input type="date"  id="dateissue" v-model="form.dateissue" placeholder="Введите дату получения">
                    <span v-if="$v.form.dateissue.$dirty && !$v.form.dateissue.required"  class="invalid-feedback">Обязательное поля для заполнения</span>
                </p>
                </div>
            </div>
            <div class="pol"><span class="fillin">*</span> Поле обязательное для заполнения.</div>
            <input type="submit" class="btn" value="Создать клиента">
        </form>
        </div>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required,alphaNum } from 'vuelidate/lib/validators'

export default {
  name: 'ClientForm',
  mixins: [validationMixin],
  data(){
      return{
            form:{
                name: null,
                surname:null,
                patronymic: null,
                datebirth: null,
                phon: "+7",
                paul: null,
                custgroup: [],
                physician: null,
                checkbtn: false,
                zipcode: null,
                country: null,
                area: null,
                city: null,
                street: null,
                house: null,
                doctype: null,
                series: null,
                number: null,
                iswhom: null,
                dateissue: null
            }
          
         }

      },
    validations:{
             form: {
                name: { required },
                surname:{ required },
                datebirth: {required},
                phon:{required,alphaNum},
                custgroup:{required},
                city:{required},
                doctype: {required},
                dateissue: {required}
            }
    },
     methods:{
        onSubmit(){
            this.$v.form.$touch()
            if(!this.$v.form.$error){
                alert("Новый клиент успешно создан")
                this.form.name = null
                this.form.surname = null
                this.form.patronymic = null
                this.form.datebirth = null
                this.form.phon = null
                this.form.paul = null
                this.form.custgroup = null                
                this.form.physician = null
                this.form.checkbtn = null
                this.form.zipcode = null
                this.form.country = null
                this.form.area = null
                this.form.city = null
                this.form.street = null
                this.form.house = null
                this.form.doctype = null
                this.form.series = null
                this.form.number = null
                this.form.iswhom = null
                this.form.dateissue = null
            }
        },
    }

}
</script>

<style lang="sass" scoped>
.form-main
    margin: 20px auto
    padding: 20px 
    max-width: 700px
    display: flex
    flex-wrap: wrap
    flex-direction: column
    background-color: white
    border: 2px dashed #d2d3d4
    .title
        font-size: 16px
        color: #1a88d6
        font-weight: 600
        margin-bottom: 10px
        text-align: left
    .form-atr
        display: flex
        flex-wrap: wrap
        margin: 10px auto
        @media (max-width: 600px)
            display: block
            margin: 0 
        p
            display: flex
            flex-direction: column
            margin: 5px
            label
                color: #606061
                text-align: left
            input
                padding: 10px 20px
                margin-top: 5px
                border: 2px solid #d4d4d4
                border-radius: 5px
                background-color: #fff
                &:focus
                    outline: none
                    border: 2px solid  #3ca1e9
            select
                padding: 10px
                margin-top: 5px 
                border: 2px solid #d4d4d4
                border-radius: 5px
                background-color: #fff
                &:focus
                    outline: none
                    border: 2px solid  #3ca1e9
            .invalid-feedback
                font-size: 12px
                color: rgb(240, 93, 93)
            .first-atr-paul
                color: red
        .flex-row
            flex-direction: row
            padding: 30px
            input
                width: 15px
                height: 15px
                margin: 0 5px
            @media (max-width: 600px)
                padding: 10px
    @media (max-width: 790px)
        max-width: 500px
.fillin
    color: rgb(240, 93, 93) 
.btn
    background-color: #3ca1e9
    font-size: 16px
    color: white
    padding: 10px 15px
    border: none
    border-radius: 5px
    cursor: pointer
    opacity: 0.9
    margin: 0 auto
    &:hover
        opacity: 1
.headr
  font-size: 26px
  padding-bottom: 30px
  color: #383838
  border-bottom: 1px solid #d2d3d4
  text-align: left
</style>