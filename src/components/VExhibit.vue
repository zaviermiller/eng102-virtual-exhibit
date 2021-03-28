<template>
  <v-container>
    <h1 class="text-h3 text-center my-12 font-weight-regular">Virtual Archive Exhibit: Pandemic Response</h1>
    <p class="text-subtitle-1 text--secondary" style="font-size: 20px !important;">{{ introduction }}</p>
    <v-row class="justify-center">
      <v-col cols="10" sm="6" md="3" lg="2" class="my-12 py-12">
        <!-- <v-btn outlined x-large>Get started</v-btn> -->
      </v-col>
      <v-col cols="12">
        <v-timeline :dense="$vuetify.breakpoint.smAndDown">
          <v-timeline-item v-for="(item) in items" :key="item.id">
            <h1  slot="opposite" :class="item.isContextual ? 'text-h4' : 'text-h3'">{{item.date}}</h1>
            <v-card v-if="!item.isContextual">
              <v-img :src="item.imgSrc" max-height="600" />
              <v-card-title>
                {{item.title}}
              </v-card-title>
              <v-card-text>
                {{item.desc}}
              </v-card-text>
            </v-card>
            <span class="text-h6" v-else>{{item.title}}</span>
          </v-timeline-item>
        </v-timeline>
      </v-col>

      <v-col cols="12">
        <h1 class="text-h3 text-center my-12 pt-12">Bibliography</h1>
        <pre style="font-size:13px;">
  The Call To Quarantine. Michigan Publishing, University Library, University of Michigan, December 14, 1918.
https://quod.lib.umich.edu/cgi/t/text/idx/f/flu/1280flu.0013.821/1/--call-to-quarantine?rgn=subject%3Bview.

  Kelly. “COVID19 & Its Effect on Education · Covid-19 Archive.” Share Your Story · A Journal of the Plague Year · Covid-19 Archive, May 26, 2020.
https://covid-19archive.org/s/archive/item/8511.

  Simkin, John. “Spartacus Educational Black Death Archive.” Spartacus Educational. Spartacus Educational, 2014.
https://spartacus-educational.com/Black_Death.htm.
        </pre>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'VirtualExhibit',

    data: () => ({
      introduction: `Over the past couple thousand years, humans have taken over the world; our above-average intelligence has let us take on the biggest predators on the planet and become the dominating life force in every environment. Surprisingly, however, the adversaries that are the hardest to conquer are the smallest. Bacteria, viruses, and other micro-organisms have proven insanely challenging to figure out, so humans have been dying of disease forever. Over time, we have gotten better at figuring out these organisms' specific properties, but we are far from the complete picture. In this virtual exhibit, I will be exploring how our understanding of viruses and other disease-causing micro-organisms has changed over time. Specifically, I will look at three distinct periods in time when circumstances were suitable for a pandemic to hit: the 1300s European "Black Death," the 1918 Influenza Epidemic, and the COVID-19 Pandemic. The earliest of these periods represents a time in human history when our understanding of what caused viruses was limited due to a lack of sufficiently advanced technology. This period of time was one of the easiest for viruses to spread; our lack of understanding and quickly-growing cities provided ample conditions for viral spread. The second represents a time when we had slightly more advanced technology but was still before the invention of vaccines and the Digital Revolution. This period may have been slightly more difficult for disease to spread since we began to understand how to better defend against these tiny killers. Finally, COVID-19 will represent modern society as we all know it, considering this pandemic is happening now, which is the ever-rising peak of human knowledge and a point at which we thought we had conquered viruses. In theory, at this point, the only thing preventing humanity from permanently ending pandemics is intrastate and interstate conflicts between nations. In the exhibit, I will inquire what the different societies did well and what they did not do well. Hopefully, by analyzing these different responses, we can get an idea of whether or not we are prepared for another pandemic. The exhibit is in the form of a timeline. The significant artifacts get their own image and summary; the timeline also has some contextual information and events, which will help us understand the humans' general knowledge over time. The purpose of this exhibit is to identify the challenges we have overcome and the ones we still have to overcome.`,
      items: [
        {
          id: "c1",
          date: 1346,
          isContextual: true,
          title: "Black Death plague hits Europe."
        },
        {
          id: "e1",
          date: 1480,
          isContextual: false,
          title: "Edward IV's Plague Medicines published.",
          imgSrc: "https://spartacus-educational.com/00blackdeath1.jpg",
          desc: 'One of the known accounts of medicinal practices used to treat the sick during the plague, Edward IV shows just how little people knew about medicine and viruses at the time. The quote I found in the archive I used detailed the process recommended for treating the disease: "A medicine for the plague... Take an egg that is newly laid, and make a hole in either end, and blow out all that is within. And lay it to the fire and let it roast till it may be ground to powder, but do not burn it. Then take a quantity of good treacle, and mix it with chives and good ale. And then make the sick drink it for three evenings and three mornings." This shows us that even though society wasn\'t new, people and medical professionals still didn\'t know that much about how viruses or the body works.'
        },
        {
          id: "c2",
          date: 1660,
          isContextual: true,
          title: "Newton invents calculus while quarantined.",
        },
        {
          id: "e3",
          date: 1918,
          isContextual: false,
          title: "LA calls to quarantine over 1918 Influenza Epidemic.",
          imgSrc: "https://quod.lib.umich.edu/cache/1/2/8/1280flu.0013.821/00000001.tif100.gif",
          desc: `This source shows the point when the 1918 Influenza virus was no longer controllable. In the call, they discuss how quarantine measures will help to prevent more death and disease. Officials say that science is useless without everyone complying with the rules. This was pretty funny to read since that has been proven in the COVID-19 pandemic today, with the whole Trump Administration and anti-maskers debacle. The artifact shows that this deadly pandemic was seriously addressed and is likely the reason this disease wasn't worse on the population than the Black Death. It also shows that despite a more significant gap in technology between now and then and then and the Black Death, the population seemed closer to preventing disease than we are.`
        },
        {
          id: "e2",
          date: 2020,
          imgSrc: "https://theintercept.imgix.net/wp-uploads/sites/1/2020/06/AP_20160177111573.jpg?auto=compress%2Cformat&q=90",
          isContextual: false,
          title: "COVID-19 changes how we live.",
          desc: "At the end of 2019, a new virus emerged. After failing to contain the threat, the world has now been going through a pandemic for over a year. Luckily, there may be an end in sight, but we may never go back to how things were before. The source here depicts a large gathering, at which all attendants must wear masks in order to mitigate viral spread. This masked society may be the new normal, as even with vaccinations the spread could remain uncontrollable. Humans know now more than ever how viruses work, so the unfortunate circumstance was probably entirely avoidable. Certain political figures seemed to not believe in the virus, which caused a cascading political rift over something as simple as whether or not something that objectively exists, exists."
        }
      ]
    }),
    methods: {
      heightFromDiff(num1, num2) {
        if (num1 > num2) {
          console.log(Math.min(500, num1 - num2))
          return num1 - num2
        } else {
          console.log( num2 - num1)
          return ( num2 - num1)
        }
      }
    }
  }
</script>
