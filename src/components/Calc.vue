<!--suppress ALL -->
<template>
  <div class="hello">
    <div class="mdl-typography--font-light mdl-typography--display-1-color-contrast">
      <div class="mdl-grid">
        <div class="mdl-cell mdl-cell--6-col mdl-cell--6-col-tablet">
          <h3 class="text-center">
            <small>starting amount</small>
          </h3>
          <input type="number" id="starting" required="required" v-model="starting"/>
        </div>
        <div class="mdl-cell mdl-cell--6-col mdl-cell--6-col-tablet">
          <h3 class="pull-right">
            <small>total saved</small>
            <br>
            $ {{totalSaved}}
          </h3>
        </div>
      </div>
      </div>
    <div>
      <div class="mdl-grid" >
        <div class="mdl-cell mdl-cell--3-col mdl-cell--6-col-tablet holder mdl-shadow--1dp" v-for="week in computedTotals">
          <div class="mdl-grid " style="padding: 0 !important;" >
            <div class="mdl-cell mdl-cell--4-col ">
              <p>
                Week #
                <br>
                <b>{{week.weekNumber}}</b>
              </p>

            </div>
            <div class="mdl-cell mdl-cell--4-col ">
              <p>
                deposit
                <br>
                <b>$ {{week.deposit.toLocaleString()}}</b>
              </p>
            </div>
            <div class="mdl-cell mdl-cell--4-col ">
            <p>
               total
              <br>
             <b>$ {{week.total.toLocaleString()}}</b>
            </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'calc',
  data() {
    return {
      data: {},
      starting: 50,
      msg: 'Starting amount',
    };
  },
  computed: {
    computedTotals: function () {
      var weeks = new Array();
      weeks[0] = [];
      weeks[0]['deposit'] = parseInt(this.starting);
      weeks[0]['total'] = parseInt(this.starting);
      weeks[0]['weekNumber'] = 1;

      for (let i = 1; i < 52; i++) {
        if (i === 1) {
          var previousIndex = 0;
        }
        else {
          var previousIndex = i - 1;
        }
        weeks[i] = [];
        weeks[i]['weekNumber'] = i + 1;
        weeks[i]['deposit'] = parseInt(this.starting) + weeks[previousIndex]['deposit'];
        weeks[i]['total'] = parseInt(this.starting) + weeks[previousIndex]['total'] + weeks[previousIndex]['deposit'];
      }
      return weeks;
    },
    totalSaved: function () {
      var lastMonth = this.computedTotals.slice(-1).pop();
      return lastMonth['total'].toLocaleString();
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
  .holder{
    background: #e8e8e8;
    padding: 10px;
    border-radius: 4px;
  }
input, textarea {
  background: none;
  color: black;
  font-size: 28px;
  padding: 10px 10px 10px 5px;
  display: block;
  width: 100%;
  border: none;
  border-radius: 0;
  border-bottom: 1px solid #c6c6c6;
  text-align: center;
}

</style>
