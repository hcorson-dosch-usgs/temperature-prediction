<template id="modeling-template">
  <div id="modeling">
    <section id="scrolly">
      <h1 class="intro__hed">
        Modeling
      </h1>
      <p> so much to say here!!</p>

      <figure ref="figure" class="sticky">
        <div id = "flubber-test">
          <svg
            id="transform-svg-test"
            xmlns="http://www.w3.org/2000/svg"
            width="auto"
            height="100%"
          >
            <g transform="translate(5 5) scale(9 9)">
              <path d="M12 17.27L18.18 21l-1.64-7.03L22 9.24l-7.19-.61L12 2 9.19 8.63 2 9.24l5.46 4.73L5.82 21z" />
              <path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z" />
              <path d="M23 5.5V20c0 2.2-1.8 4-4 4h-7.3c-1.08 0-2.1-.43-2.85-1.19L1 14.83s1.26-1.23 1.3-1.25c.22-.19.49-.29.79-.29.22 0 .42.06.6.16.04.01 4.31 2.46 4.31 2.46V4c0-.83.67-1.5 1.5-1.5S11 3.17 11 4v7h1V1.5c0-.83.67-1.5 1.5-1.5S15 .67 15 1.5V11h1V2.5c0-.83.67-1.5 1.5-1.5s1.5.67 1.5 1.5V11h1V5.5c0-.83.67-1.5 1.5-1.5s1.5.67 1.5 1.5z" />
              <path d="M21 16v-2l-8-5V3.5c0-.83-.67-1.5-1.5-1.5S10 2.67 10 3.5V9l-8 5v2l8-2.5V19l-2 1.5V22l3.5-1 3.5 1v-1.5L13 19v-5.5l8 2.5z" />
              <path d="M7 2v11h3v9l7-12h-4l4-8z" />
              <path d="M12 3v10.55c-.59-.34-1.27-.55-2-.55-2.21 0-4 1.79-4 4s1.79 4 4 4 4-1.79 4-4V7h4V3h-6z" />
              <path
                d="M6.54,0C6.24,0,6.05,0.18,5.92,0.38L0.08,9.92C0,10,0,10.15,0,10.31C0,10.85,0.38,11,0.69,11h11.62
        c0.38,0,0.69-0.15,0.69-0.69c0-0.15,0-0.23-0.08-0.38L7.15,0.38C7.03,0.18,6.79,0,6.54,0z"
              />
              <path d= "M1 5 L11 5 L11 10 L1 10z" />
              <path d= "M5 5 L16 10 L5 15 L1 10z" />
            </g>
          </svg>
        </div>
        <div id="bees-container">
          <div id="progress-container">
          <p class="progress"/>
          </div>
        </div>
      </figure>
      <div id="button-container">
        <h4>Color By</h4>
        <button
          id="clear"
          class="cbutton active"
          @click="recolor('none')"
        >
          Clear
        </button>
        <button
          id="seg_id_nat"
          class="cbutton"
          @click="recolor('seg_id_nat')"
        >
          Segment
        </button>
        <button
          id="year"
          class="cbutton"
          @click="recolor('year')"
        >
          Data Year
        </button>
        <button
          id="month"
          class="cbutton"
          @click="recolor('month')"
        >
          Data Month
        </button>         
      </div>
      <article>
        <div class="step-container">
          <div
            class="step"
            data-step="1"
          >
            <p>Each dot is a monthly RMSE.</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="1"
          >
            <p>RMSE is one way to measure model error/accuracy. RMSE quantifies the distance between predicted and observed values.</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="1"
          >
            <p>Models with RMSE values closer to zero do better at predicting temeprature than models with higher RMSE.</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="2"
          >
            <p>ANN</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="3"
          >
            <p>RNN uses time.</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="4"
          >
            <p>RGCN adds space.</p>
          </div>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="5"
          />
          <p>RGCN + pretraining</p>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="6"
          />
          <p>and that's how we do it!</p>
        </div>
        <div class="step-container">
          <div
            class="step"
            data-step="7"
          />
          <p />
        </div>
      </article>
    </section>
    <section id="outro">
      <h2>bye</h2>
    </section>
  </div>
</template>

<script>
    import * as d3Base from "d3";
    import * as scrollama from 'scrollama';
    import * as flubber from "flubber";

  export default {
    name: 'Modeling',
    name: 'TransformSVG',
    components: {
    },
    data() {
          return {
            publicPath: process.env.BASE_URL, // this is need for the data files in the public folder, this allows the application to find the files when on different deployment roots
            d3: null, // this is used so that we can assign d3 plugins to the d3 instance
            // global variables instantiated in next section
            margin: 20,
            width: 400,
            height: 300,
            marginX: 20,
            marginY: 20,
            radius: 5,
            force_sim: null,
            bees: null,
            xScale: null,
            scroller: scrollama(), 
            step: 0,
            progress: 0,
            model_sel: null,
            init_decay: null,
            activeButton: null,
            seg_id_nat: null,
            year: null,
            month: null,
            pathStrings: null,
            
          }
        },
         watch: {
          activeButton: {
            deep: true,
            handler() {this.recolor(); }
          }
        },
        mounted() {
          this.scroller.setup({
                  step: "#scrolly article .step",
                  debug: false,
                  offset: 0.5,
                  progress: true,
                })
                .onStepEnter(this.handleStepEnter)
                .onStepProgress(this.handleStepProgress)
                .onStepExit(this.handleStepExit);

          // 3. setup resize event...
          this.resize();
          window.addEventListener("resize", this.resize);

          this.d3 = Object.assign(d3Base); // this loads d3 plugins with webpack
          this.paddedRadius = 7;
          
          // define flubber variables - set each d attribute of each path as an element in an array of path strings
          this.pathStrings = Array.from(document.querySelectorAll("#transform-svg-test path")).map(d => d.getAttribute("d"));

          this.getData(); //read in data and then draw chart

        },
        //methods are executed once, not cached as computed properties, rerun everytime deal with new step
        methods: {
          getData() {
            const self = this;

            let promises = [self.d3.csv(self.publicPath + "data/beeswarm_monthly_rmse_cast.csv")];
            Promise.all(promises).then(self.callback);

          },
          callback(data) {
            this.setFlubber();

            let rmse_monthly = data[0];
            
            // calculate value arrays for color coding ONCE here and then we're good forever
            this.seg_id_nat = [...new Set(rmse_monthly.map(item => item.seg_id_nat))];
            this.year = [...new Set(rmse_monthly.map(item => item.year))];
            this.month = [...new Set(rmse_monthly.map(item => item.month))];
            
            var model_list = ['ANN','RNN','RGCN','ANN', 'RNN', 'RGCN', 'RGCN_ptrn','RGCN_ptrn','ANN'];
            var data_set = model_list[this.step];
            this.setChart(rmse_monthly, data_set);

          },
          // resize to keep scroller accurate
          resize () {
            const self = this;
            const bounds = this.$refs.figure.getBoundingClientRect()
            this.width = bounds.width
            this.height = bounds.height
            this.marginX = bounds.width * 0.1
            this.marginY = bounds.height * 0.1
            this.scroller.resize()
          },
          // set up flubber svg
          setFlubber() {
            const self = this;

            // display only the first path element
            self.d3.select("#transform-svg-test")
                .selectAll("path")
                .filter(function(d, i) {
                    return i; })
                .remove();
          },
          // animate flubber svg
          animateFlubber() {
            const self = this;

            // remove the first pathstring from the array and set it as the starting path
            let start = self.pathStrings.shift(),
                // set the first element of the modified array as the ending point
                end = self.pathStrings[0];

            // place the path string you removed at the end of the array                
            self.pathStrings.push(start);

            // transition between the pre-defined starting path and ending path
            self.d3.select("#transform-svg-test path")
              .style("display", "block")
              .datum({ start, end })
              .transition()
              .duration(1200)
              .attrTween("d", function(d){
                  return flubber.interpolate(d.start, d.end, { maxSegmentLength: 0.1 })
              })
          },
          // draw beeswarm/scatterplot
          setChart(data, model) {
            const self = this;
            
            // Set some forces
            var forceStrength = .3;
            var gravityStrength = 1;
            var friction = 0.6;
            var alpha = .12; // similar to "starting temperature", higher is hotter
            var alphaDecay = 0; // similar to "cool down rate", higher is faster
            var xForceStrength = 2;
            var yForceStrength = .05;
            var timeBeforeKill = 3000;

        // append svg
          this.bees = this.d3.select("#bees-container").append("svg")
            .attr("viewBox", [0, 0, (this.width+this.marginX+this.marginX), (this.height+this.marginY+this.marginY)].join(' '))
            .attr("width", this.width)
            .attr("height", this.height)
            .attr("class", "bees_dotPlot");

          this.bees.append("line", 'svg')
            .classed("main_line", true)
            .attr("x1", this.marginX)
            .attr("y1", this.height/2)
            .attr("x2", this.width-this.marginX)
            .attr("y2", this.height/2)
            .attr("stroke-width", 1.5)
            .attr("stroke", "#A3A0A6");
            
          //scale x axis
          this.xScale = this.d3.scaleLinear()
            .range([this.marginX, this.width - this.marginX])
            .domain([0,7]);

          //draw bees
          //use force to push each dot to x position
          this.bees.selectAll("dot")
            .data(data)
          .enter().append("circle").classed('dot', true)
            .attr("r", this.radius)
            .attr("fill", "orchid")
            .attr("opacity", .8)
            .attr('cx', function(d){return self.xScale(d[model]);})
            .attr('cy', function(d){return this.height/2;})

          //apply force to push dots towards central position on yaxis
          this.force_sim = this.d3.forceSimulation(data)
            .force('x', this.d3.forceX(function(d){
                return self.xScale(d[model])
              }).strength(xForceStrength)
            )
            .force('y', this.d3.forceY(this.height/2).strength(yForceStrength))	
            .force('collide', this.d3.forceCollide(this.paddedRadius).strength(1))
            // .force("charge", d3.forceManyBody().strength(gravityStrength))
            .alpha(alpha)
            .alphaDecay(alphaDecay)
            .velocityDecay(friction)
            .on('tick', self.tick);

            //add decay after set time to smoothly end transition

            this.init_decay = setTimeout(function(){
              console.log('init alpha decay')
              this.force_sim
                .alphaDecay(alphaDecay);
            }, timeBeforeKill);

            // add x axis
            this.bees.append("g")
              .attr("transform", "translate(0," + this.height + ")")
              .attr("stroke-width", "2px")
              .call(this.d3.axisBottom(self.xScale));

          },
          recolor(activeButton){
            const self = this;
            var transitionTime = 1000; // how long it takes for the color to change

            // BUTTON FUNCTIONALITY
            // select the button with class "active"
            var prevButton = this.d3.select(".active");
            // remove active class from all buttons
            this.d3.selectAll('.cbutton').classed('active', false);
            // Find the button just clicked and give it a class "active"
            this.d3.select("#"+activeButton).classed('active', true);

            // MAKE COLOR RAMPS

            var interpolateColors = this.d3.scaleSequential(this.d3.interpolateWarm);

            //interpolate the color scale to have that many stops
            var colorScale = this.d3.scaleOrdinal((this.d3.schemePastel2));  // This is the one currently hooked up, and it's not really working properly right now. 

            // RECOLORING THE CHART
            if(activeButton == "none") {
              this.d3.selectAll(".dot")
                .transition()
                .duration(transitionTime/5)
                .style('fill', "white");
            } else if (activeButton == "seg_id_nat" || "year" || "month") {
              console.log("color me by", activeButton, "and here's the data", this[activeButton]);
              interpolateColors.domain(this[activeButton])
              this.d3.selectAll(".dot")
                .transition()
                .duration(transitionTime/5)
                .style('fill', function(d) { return interpolateColors(d[activeButton])});
            } 

          },

          //update x position on scroll
          updateChart(data) {
            const self = this;
            // list models in order of transitions, use step index to select
            var model_list = ['ANN','RNN','RGCN','ANN', 'RNN', 'RGCN', 'RGCN_ptrn','RNN','ANN'];
            var color_list = ['pink','teal','lightgreen','goldenrod','orangered','cadetblue','orchid','blue','transparent'];
            var color_sel = color_list[data];
            var model_sel = model_list[data];

            this.force_sim.force('x', this.d3.forceX(function(d){
                return self.xScale(d[model_sel])
            }).strength(1))

            this.force_sim
              .alphaDecay(0.01)
              .alpha(0.12)
              .restart()
              .on('tick', self.tick);

            clearTimeout(this.init_decay);

            this.init_decay = setTimeout(function(){
              console.log('re-init alpha decay');
              this.force_sim.alphaDecay(0.1);
            }, 3000)

            this.d3.selectAll(".dot")
              .transition()
                .duration(1000)
                .style('fill', color_sel)

          },
          tick() {
          const self = this;
          this.d3.selectAll(".dot")
            .attr('cx', function(d){return d.x})
            .attr('cy', function(d){return d.y})
        },
        // scrollama event handler functions

        // add class on enter
        handleStepEnter(response) {
          const self = this;
          // response = { element, direction, index }
          console.log(response);
           // changes css for class
          response.element.classList.add("is-active");

          //update number in sticky to show step number
          self.d3.select("#bees-container p")
          .text(response.index + 1);

          this.animateFlubber();

          this.updateChart(response.index);

        },
        
        // add remove class on exit
        handleStepExit(response) {
          const self = this;
          // response = { element, direction, index }
          console.log(response);
          // changes css for class
          response.element.classList.remove("is-active");
        },
        // track scroll progress - not returning anything?
        handleStepProgress(response) {
          //console.log(response.progress);
        }
    }
  }
</script>

<style scoped lang="scss">
#modeling, #modeling-template {
  text-align: center;
}
#progress-container {
  position: relative;
  width:80%;
  height: 30px;
  margin-left:10%;
  line-height: 2em;
}
.progress {
  position: relative;
  background-color:transparent;
  top:1%;
  left:50%;
  font-size: .51em;
  line-height: 1em;
  color: red;
}
#scrolly {
   position: relative;
}

article {
  position: relative;
  margin: 0 auto;
  width: 100%;
}
.sticky {
  position: -webkit-sticky;
  position: sticky;
  top:20vh;
  height: 60vh;
  padding: 1em;
  left: 0;
  margin: 0;
  color: white;
  width: 100vw;
  z-index: 0;
  
}
.sticky h2 {
  text-align: center;
  position: relative;
  top: 40vh;
}

#button-container {
    z-index: 100;
    bottom: 0;
    position: -webkit-sticky;
    position: sticky;
    top: 85vh;
    .cbutton{
        display: inline-block;
        background-color: black;
        color: #DBDAD9;
        padding: 10px;
        margin:0 10px 10px 0;
        border:0.1em solid #DBDAD9;
        border-radius:0.12em;
        box-sizing: border-box;
        text-decoration:none;
        text-align:center;
        transition: all 0.2s;
        min-width: 110px;
        cursor: pointer;
        font-size: .8em;
    }
    .cbutton.active {
      background: #DBDAD9;
      color: #000000;
    }
    .cbutton:focus {
      outline: 0;
    }
    .cbutton:hover {
      color:#000000;
      background-color:#DBDAD9;
    }


  }

.step-container {
  width:100vw;
}
.step {
  position: relative;
  width: 90%;
  margin: 50rem auto 4rem auto;
  color:white;
  z-index: 1;
  height: 50vh;
}

// can trigger attribute changes with .is-active
.step.is-active {
  color: orange;
}

// could add changes by step here
.step.is-active[data-step="1"] {
}
.step.is-active[data-step="2"] {
}
.step.is-active[data-step="3"] {
}
.step.is-active[data-step="4"] {
}
.step.is-active[data-step="7"] {
  margin-bottom: 600px;
}
.step:last-child {
  margin-bottom: 600px;
}


.step p {
  text-align: center;
  padding: 1rem;
  font-size: 2.5rem;
}
#outro {
  text-align: center;
  width: 100%;
  height: 400px;
}
#bees-container {
  position: absolute;
  width: 90%;
  height: 60%;
  left: 5%;
  top: 40%;

}
#flubber-test {
  stroke: #ffffff;
  stroke-width: 0.5px;
  position: absolute;
  width: 90%;
  height: 40%;
  left: 5%;
  top: 0%;
}
</style>