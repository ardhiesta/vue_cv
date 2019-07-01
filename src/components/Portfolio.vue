<template>
  <v-container fluid fill-height>
    <v-flex xs12 sm6 offset-sm3>
      <v-card>
        <v-img
          src="https://scontent-sin2-2.xx.fbcdn.net/v/t1.0-9/fr/cp0/e15/q65/424349_4233350202848_2098649017_n.jpg?_nc_cat=101&efg=eyJpIjoiYiJ9&_nc_ht=scontent-sin2-2.xx&oh=d45aba9b9a814b883f077fba3a8cd887&oe=5DBDDCF6"
          height="300px"
        >
          <v-layout align-center justify-center>
            <!--v-card-title>
              <v-btn dark icon>
                <v-icon>chevron_left</v-icon>
              </v-btn>

              <v-spacer></v-spacer>

              <v-btn dark icon class="mr-3">
                <v-icon>edit</v-icon>
              </v-btn>

              <v-btn dark icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-card-title-->

            <v-spacer></v-spacer>

            <v-card-title class="white--text pl-5 pt-5">
              <div class="display-1 pl-5 pt-5">Ardhi Wijayanto</div>
            </v-card-title>
          </v-layout>
        </v-img>

        <v-list two-line>
          <v-list-tile @click>
            <v-list-tile-action>
              <v-icon color="indigo">mail</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>Lecturer at Universitas Sebelas Maret</v-list-tile-title>
              <v-list-tile-sub-title>ardhi.wijayanto@staff.uns.ac.id</v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>

          <v-divider inset></v-divider>
          
          <v-list-tile @click>
            <v-list-tile-action>
              <v-icon color="indigo">phone</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>085645******</v-list-tile-title>
              <v-list-tile-sub-title>Mobile</v-list-tile-sub-title>
            </v-list-tile-content>

            <v-list-tile-action>
              <v-icon>chat</v-icon>
            </v-list-tile-action>
          </v-list-tile>

          <v-divider inset></v-divider>

          <v-list-tile @click>
            <v-list-tile-action>
              <v-icon color="indigo">location_on</v-icon>
            </v-list-tile-action>

            <v-list-tile-content>
              <v-list-tile-title>Perumahan XYZ</v-list-tile-title>
              <v-list-tile-sub-title>Tasikmadu, Karanganyar</v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
        <v-card>
          <v-list>
            <v-list-group
              v-for="item in items"
              :key="item.title"
              v-model="item.active"
              :prepend-icon="item.action"
              no-action
            >
              <template v-slot:activator>
                <v-list-tile>
                  <v-list-tile-content>
                    <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                  </v-list-tile-content>
                </v-list-tile>
              </template>

              <v-list-tile v-for="subItem in item.items" :key="subItem.title" @click>
                <v-list-tile-content>
                  <v-list-tile-title>{{ subItem.title }}</v-list-tile-title>
                </v-list-tile-content>

                <v-list-tile-action>
                  <v-icon>{{ subItem.action }}</v-icon>
                </v-list-tile-action>
              </v-list-tile>
            </v-list-group>
          </v-list>
        </v-card>
      </v-card>
    </v-flex>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    drawer: null
  }),
  props: {
    source: String
  },
  data() {
    return {
      items: [
        {
          action: "school",
          title: "Pendidikan",
          items: [
            { title: "S1 Informatika UNS (2007-2011)" },
            { title: "S2 Ilmu Komputer UGM (2013-2017)" }
          ]
        },
        {
          action: "work",
          title: "Pengalaman Kerja",
          items: [
            { title: "Java developer - PT Unibit Polamaya (2012-2014)" },
            { title: "Android developer - Wonderlabs (2016)" },
            {
              title:
                "Dosen D3 Manajemen Informatika - Universitas Merdeka Madiun (2017)"
            },
            { title: "Dosen S1 Informatika - UNS (2018 - sekarang)" }
          ]
        },
        {
          action: "code",
          title: "Bahasa Pemrograman",
          items: [
            { title: "Android" },
            { title: "PHP" },
            { title: "JS" },
            { title: "Python" }
          ]
        }
      ]
    };
  }
};
</script>