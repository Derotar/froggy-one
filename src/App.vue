<script setup lang="ts">
import { NCarousel } from "naive-ui";

const handleFrogClick = () => {
  const audio = new Audio("/audio/frog.mp3");
  audio.volume = Math.random();
  audio.play();

  const froggySize = 100 + 300 * Math.random();

  const monet = () => -0.5 + Math.random() > 0;

  const isFroggySideX = monet();
  const isFroggyTop = monet();
  const isFroggyLeft = monet();

  const froggySidePosition = isFroggySideX
    ? window.innerHeight * Math.random()
    : window.innerWidth * Math.random();

  //lets create froggies at corners of screen
  const img = document.createElement("img");
  img.src = "/img/froggy.png";
  img.style.cssText = `
    position: fixed;
    top: ${
      isFroggySideX ? `${froggySidePosition}px` : isFroggyTop ? "0px" : `100%`
    };
    left: ${
      isFroggySideX
        ? isFroggyLeft
          ? "0px"
          : `100%`
        : `${froggySidePosition}px`
    };
    z-index: 50;
    width: ${froggySize}px;
    height: auto;
    transform: translate(-50%,-50%) ${
      !isFroggySideX && isFroggyTop ? "scaleY(-1)" : ""
    } ${isFroggySideX && isFroggyLeft ? "scaleX(-1)" : ""};
  `;

  document.body.append(img);
  setTimeout(() => img.remove(), 1000);
};
</script>

<template>
  <div class="w-full flex flex-col max-w-[1240px] mx-auto px-4 gap-4">
    <div
      class="flex w-full lg:flex-row items-center justify-center pt-[64px] pb-[32px]"
    >
      <img
        src="/img/froggy.png"
        alt="froggy-png"
        class="w-[150px] lg:w-[200px] h-auto shrink-0 cursor-pointer hover:scale-105 transition-all ease-linear duration-200"
        @click="handleFrogClick"
      />

      <h1 class="relative z-10 left-[-1em] text-4xl lg:text-6xl">
        Froggy<br class="block lg:hidden" />
        one
      </h1>
    </div>

    <p>Здесь описание того, куда я хожу, и что я узнал новенького за эти дни</p>
    <p>
      Да, собственно есть, инстаграм или телеграмм, но это все же не то, что бы
      я хотел для себя
    </p>
    <p>
      Всякие вещи, которые я хочу, я буду размещать тут, т.к мне дико этого
      хочется, иметь реально свое занятие и свои страсти
    </p>

    <section>
      <h2>Дата 23.02.2025</h2>

      <NCarousel show-arrow class="rounded-[24px] w-full max-w-[300px]">
        <img class="w-full h-[200px] object-cover" src="/img/froggy.png" />
      </NCarousel>

      <p>
        Сегодня я досмотрел до конца
        <a
          href="https://www.youtube.com/watch?v=8OHe6chCWTE&t=260s"
          target="_blank"
          class="text-blue-600 underline"
          >видос ульби</a
        >
        по деплою сайта, оч доволен
      </p>
      <p>Добавил жабок, которые вылезают по бокам, мне очень понравилось</p>
      <p>
        Неважно себя чувствую, но разузнал, про то, куда я хочу пойти и потащить
        пацанов на день рождения
      </p>
      <p>
        Решил купить на горбушке onyx boox note air 4c, не уверен честно насчет
        выбора цвета, но распознавание текста, цена там, и тд, заставляют меня
        склониться к покупке именно этого аппарата. А не, например,
        <b>onyx boox ultra tab pro</b> или <b>remarkable paper pro</b>
      </p>

      <p>
        Перестраиваю свой рацион, скушал сегодня кусочек муксуна, поел хлебцев
        рисовых в виде бутербродов, и скушал долму в консервах, вышло очень даже
        неплохо
      </p>
      <p>По калориям и белку все вроде ок</p>
      <p>В целом, большой молодец! Особенно за деплой сайта</p>
      <p>Еще посмотрел кучу серий интернов, где то 1 сезон, 60-80 серии</p>
    </section>

    <section>
      <h2>Дата 22.02.2025</h2>

      <NCarousel show-arrow class="rounded-[24px] w-full max-w-[300px]">
        <img class="w-full h-[200px] object-cover" src="/img/content/1.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/2.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/3.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/4.png" />
      </NCarousel>

      <p>
        В этот день я ходил на выставку водного человека. Не знал точно, что
        меня там ждет, вообще я искал выставки одежды, чтобы посмотреть на
        интересные штуки и подобная выставка меня смущала.
      </p>

      <p>
        Там было очень много дайверов, разных программ дайвинга, продажи
        костюмов, техники, средств для ушей, массаж какой-то странный, выставка
        картин, игрушки, Издательство "Самокат", продажа устриц и арктической
        рыбы всякой, это было круто
      </p>

      <p>
        Там было как раз чем наградить себя за прошедшую неделю, я купил
        копченого муксуна, две книжки в издательстве самокат, алтайского варенья
        без сахара: с черникой, брусникой и клюквой. И купил себе желтую кофту
        из Captain's Morgan. Конечно, до конца не уверен, нравится мне она или
        нет, но с чайкой были только женские, что грустно
      </p>
    </section>

    <section>
      <h2>Дата 22.02.2025</h2>

      <NCarousel show-arrow class="rounded-[24px] w-full max-w-[300px]">
        <img class="w-full h-[200px] object-cover" src="/img/content/1.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/2.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/3.png" />
        <img class="w-full h-[200px] object-cover" src="/img/content/4.png" />
      </NCarousel>

      <p>Приехали мои жабки!!!</p>
    </section>
  </div>
</template>

<style scoped></style>
