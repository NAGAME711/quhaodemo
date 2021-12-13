    <v-autocomplete
              v-model="friends"
              :items="people"
              filled
              chips
              item-text="name"
              item-value="name"
              multiple
            >
              <template v-slot:selection="data">
                <v-chip
                  v-bind="data.attrs"
                  :input-value="data.selected"
                  close
                  @click="data.select"
                  @click:close="remove(data.item)"
                >
                  {{ data.item.name }}
                </v-chip>
              </template>            
            </v-autocomplete>
            
      ----------------------------------------------------------------
      
      data
      
      -----------------------------------------------------------------
            
      people: [
      { header: "Group 1" },
      { name: "Sandra Adams", group: "Group 1" },
      { name: "Ali Connors", group: "Group 1"},
      { name: "Trevor Hansen", group: "Group 1"},
      { name: "Tucker Smith", group: "Group 1"},
      { divider: true },
      { header: "Group 2" },
      { name: "Britta Holt", group: "Group 2"},
      { name: "Jane Smith ", group: "Group 2" },
      { name: "John Smith", group: "Group 2" },
      { name: "Sandra Williams", group: "Group 2"},
    ],
    
      ----------------------------------------------------------------
      
      methods
      
      -----------------------------------------------------------------
      remove(item) {
      const index = this.friends.indexOf(item.name);
      if (index >= 0) this.friends.splice(index, 1);
    },
