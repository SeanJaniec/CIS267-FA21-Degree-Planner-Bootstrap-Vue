<template>
<div class="col-lg-6 semester-schedules">
            <h3>Semester Schedules</h3>

            <div
              v-for="schedule in schedules"
              v-bind:key="schedule.id"
              class="accordion my-4"
              id="schedule.id"
            >
              <div class="accordion-item">
                <h2
                  class="accordion-header"
                  id="fall2019heading"
                  v-b-toggle:[schedule.collapseId]
                >
                  <div class="">
                    <h4 class="my-0">{{ schedule.name }}</h4>
                  </div>
                </h2>
                <b-collapse :id="schedule.collapseId">
                  <div class="accordion-body">
                    <table class="table table-hover">
                      <thead>
                        <th>Course</th>
                        <td></td>
                        <td></td>
                        <th>Credits</th>
                      </thead>
                      <tr  
                      v-for="classes in schedule.classes"
                        v-bind:key="classes.id">
                        
                        <td>{{ classes["Course ID"] }}</td>
                        <td>
                          <span class="fw-bold">  </span>
                        </td>
                        <td>
                          <span class="badge bg-primary"> {{ classes["Category"] }} </span>
                        </td>
                        <td>{{ classes["Credit Hours"] }}</td>
                      </tr>
                      <!-- <tr>
                        <td>CIS 171</td>
                        <td>
                          <span class="fw-bold">Computer Programming I</span>
                        </td>
                        <td>
                          <span class="badge bg-secondary"> CS </span>
                        </td>
                        <td>3</td>
                      </tr>
                      <tr>
                        <td>COM 140</td>
                        <td>
                          <span class="fw-bold">Speech</span>
                        </td>
                        <td>
                          <span class="badge bg-primary"> LAC </span>
                        </td>
                        <td>3</td>
                      </tr>
                      <tr>
                        <td>CYB 101</td>
                        <td>
                          <span class="fw-bold">Intro to Cybersecurity</span>
                        </td>
                        <td></td>
                        <td>3</td>
                      </tr>
                      <tr>
                        <td>MAT 120</td>
                        <td>
                          <span class="fw-bold">Precalculus</span>
                        </td>
                        <td></td>
                        <td>3</td>
                      </tr>
                      <tr>
                        <td></td>
                        <td></td>
                        <td></td>
                        <td class="fw-bold">14</td>
                      </tr> -->
                    </table>
                  </div>
                </b-collapse>
              </div>
            </div>
          </div>
</template>

<script>
export default {
    name: "SemesterSchedule",
    props: {
        schedules: Array
    }

}
</script>

<style>

</style>