<script setup lang="ts">
import { ref } from 'vue'
import { ElDialog } from 'element-plus'
import { BottomLeft } from '@element-plus/icons-vue'
interface Section {
  title: string
  subtitle: string
  points: string[]
}

const sections: Section[] = [
  {
    title: 'Медицинские осмотры\n',
    subtitle: 'При приеме на работу',
    points: [
      'Полное обследование кандидатов',
      'Определение профпригодности',
      'Оформление медицинских заключений'
    ]
  },
  {
    title: 'Медицинские освидетельствования\n',
    subtitle: 'Плановые обследования персонала',
    points: [
      'График, согласованный с предприятием',
      'Выявление профзаболеваний на ранних стадиях',
      'Осмотры стажированного контингента'
    ]
  },
  {
    title: 'Консультации специалистов\n',
    subtitle: 'Для водителей и других специальностей',
    points: [
      'Оперативный вывод на линию',
      'Внедрение современных медицинских комплексов',
      'Формирование электронных путевых листов'
    ]
  },
  {
    title: 'Лабораторные исследования\n',
    subtitle: 'Для ответственных должностей',
    points: [
      'Тестирование скорости реакции',
      'Проверка когнитивных функций',
      'Оценка стрессоустойчивости'
    ]
  },
  {
    title: 'Психофизиологическое обследование\n',
    subtitle: 'Для всех контрагентов',
    points: [
      'Защита персональных данных работников',
      'Безопасный обмен списками',
      'Оперативное получение заключений'
    ]
  },
  {
    title: 'Комплексные программы оздоровления\n',
    subtitle: 'Для всех контрагентов',
    points: [
      'Защита персональных данных работников',
      'Безопасный обмен списками',
      'Оперативное получение заключений'
    ]
  },
  {
    title: 'Телемедицинские консультации\n',
    subtitle: 'Для всех контрагентов',
    points: [
      'Защита персональных данных работников',
      'Безопасный обмен списками',
      'Оперативное получение заключений'
    ]
  },
  {
    title: 'Защищенный электронный документооборот\n',
    subtitle: 'Для всех контрагентов',
    points: [
      'Защита персональных данных работников',
      'Безопасный обмен списками',
      'Оперативное получение заключений'
    ]
  },
]

const dialogVisible = ref(false)
const activeSection = ref<Section | null>(null)

const openModal = (section: Section) => {
  activeSection.value = section
  dialogVisible.value = true
}
</script>



<template>
  <div class="feat bg-gray pt-5 pb-5" style="background: #f5f5f5">
    <el-main>
    <div class="container">
      <div class="section-head col-sm-12">
        <h4 class="ffdd"><span class="h4h4">что мы предлагаем</span></h4>
      </div>

      <div class="grid-container">
        <div
          v-for="(section, index) in sections"
          :key="index"
          class="grid-item"
          @click="openModal(section)"
        >
          <div class="icon-wrapper">
            <el-icon><BottomLeft /></el-icon>
          </div>
          <div class="item-title">{{ section.title }}</div>
        </div>
      </div>

      <el-dialog v-model="dialogVisible" :title="activeSection?.title" >
        <template #default>
          <p><strong class="frfr">{{ activeSection?.subtitle }}</strong></p>
          <ul class="dede">
            <li style="list-style-type: decimal;" v-for="(point, i) in activeSection?.points" :key="i">{{ point }}</li>
          </ul>
        </template>
      </el-dialog>
    </div>
      </el-main>
  </div>
</template>


<style scoped>
.ffdd{
  margin-bottom: 6%;
}

.frfr{
  font-size: 39px;
  font-weight: 500;
  color: black;
}
.h4h4{
  vertical-align: middle;
  color: #000000;
  font-size: 84px;
  font-family: 'HelveticaNeue', Arial, sans-serif;
  line-height: 1.2;
  font-weight: 400;
  background-position: center center;
  border-color: transparent;
  border-style: solid;
  transform-origin: center center;
  line-height: 60px;
}

.el-dialog__title{
  font-size: 40px;
  font-weight: 600;

}
.el-dialog{
  padding: 36px;
}
.dede{
  font-size: 34px;
  color: black;
}

.el-dialog__headerbtn .el-dialog__close{
  color: #e72d50 !important;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(4, 1fr); /* по умолчанию 4 */
  gap: 20px;
  margin-top: 40px;
}

.grid-item {
  position: relative;
  background-color: #ffffff;
  padding: 45px;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
  font-weight: 600;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.06);
  min-height: 192px;
  display: flex;
  padding-left: 25px;
  flex-direction: column;
  justify-content: flex-end;
}
.el-main{
  padding: 60px 10% !important;
}

.grid-item:hover {
  background-color: #0D72b9;
  color: white;
  transform: scale(1.03);
}

.item-title {

    font-weight: 600;
    text-align: left;
    position: relative;
    top: -3px;
    height: 110px;
    display: flex
;
    align-items: flex-start;
    justify-content: flex-start;
    line-height: 1.2;
    white-space: normal;
    word-break: break-word;
}


.item-title {
  font-size: clamp(18px, 2vw, 36px); /* от 18 до 36px */
}

.h4h4 {
  font-size: clamp(32px, 6vw, 84px);
}

.el-dialog__title {
  font-size: clamp(20px, 4vw, 40px);
}

.frfr {
  font-size: clamp(18px, 3vw, 39px);
}

.dede {
  font-size: clamp(16px, 2.8vw, 34px);
}


.icon-wrapper {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 67px;
}
.el-main{
  padding: 60px;
}

@media (max-width: 1024px) {
  .grid-container {
    grid-template-columns: repeat(2, 1fr);
  }
.item-title{
  height: 45px;
}
.grid-item{
      min-height: 49px;
}
.icon-wrapper{
      font-size: 47px;
}



}


/* Адаптация */
@media (max-width: 768px) {
  .grid-container {
    display: contents;
  }
  .grid-item{
    margin-top: 10px;
  }
  .h4h4{
    font-size: 27px;
  }
  .el-main{
padding: 16px !important;
  }




.item-title {
    font-size: 18px;
    font-weight: 600;
    text-align: left;
    position: relative;
    display: flex;
    justify-content: flex-start;
    line-height: 1.2;
    white-space: normal;
    word-break: break-word;
        height: 73px;
                align-items: anchor-center;
                        width: 83%;
}
.grid-item[data-v-ecd4fbd9] {
    position: relative;
    background-color: #ffffff;
    padding: 16px;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
    font-weight: 600;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.06);
    min-height: 74px;
    flex-direction: column;
    justify-content: flex-end;
}
.icon-wrapper[data-v-ecd4fbd9] {
    position: absolute;
    top: 25px;
    right: 10px;
    font-size: 40px;
}

}
</style>

