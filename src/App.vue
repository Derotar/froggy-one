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
  <div class="w-full flex flex-col max-w-[1240px] mx-auto">
    <div class="flex w-full items-center justify-center pt-[64px] pb-[32px]">
      <img
        src="/img/froggy.png"
        alt="froggy-png"
        class="w-[200px] h-auto shrink-0 cursor-pointer hover:scale-105 transition-all ease-linear duration-200"
        @click="handleFrogClick"
      />

      <h1 class="relative z-10 left-[-1em] text-6xl">Froggy one</h1>
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
