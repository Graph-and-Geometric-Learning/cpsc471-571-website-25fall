<template>
    <v-container>
        <v-row>
            <v-col>
                <v-sheet class="pa-8" elevation="6">
                    <h1>Welcom to CPSC 4710/5710!</h1>
                    <ul>
                        <li>The classes meets on Tuesday/Thursday 4PM-5:15PM ET, <a href="https://map.yale.edu/?id=1910#!m/591737?share" target="_blank">DAVIES AUD</a> - Davies Auditorium, Becton Ctr AUD.
                          <ul>
                            <li>Most of the lecture will be in-person.</li>
                            <li>There will be a few guest lectures, some of which might be held remotely.</li>
                          </ul>
                        </li>
                        <li>This is a semilar-like, graduate-level course.
                            <ul>
                                <li>Students are expected to master the background of deep learning, and are expected to have the ability to explore cutting-edge research topics on their own.</li>
                            </ul>
                        </li>
                        <li>This is a relatively new course, and feedbacks are especially welcomed!</li>
                        <li>Slides will be posted here before classes.</li>

                    </ul>
                </v-sheet>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-sheet class="pa-8" elevation="6">
                    <h1>Prerequisites</h1>
                    <ul>
                        <li>The course has relevance to a wide range of topics and background in DL is needed!</li>
                        <li>Trustworthy DL for different architectures will all be in scope of the class.</li>
                        <ul>
                            <li>However, although beneficial, students are not required to understand all model architectures.</li>
                            <li>The course will give a brief overview of common model architectures.</li>
                        </ul>
                        <li>Minimum prerequisites
                            <ul>
                                <li><a href="https://courses.yale.edu/?keyword=CPSC%20201&srcdb=999999">CPSC 201</a>, <a href="https://courses.yale.edu/?keyword=CPSC%20223&srcdb=999999">CPSC 223</a> and one of <a href="https://courses.yale.edu/?keyword=S&DS%20265&srcdb=guide2023&dept=S&DS">S&DS 265a</a>, <a href="https://courses.yale.edu/?keyword=CPSC%20381&srcdb=guide2023&dept=CPSC">CPSC 381/581</a>, and <a href="https://courses.yale.edu/?keyword=CPSC%20452&srcdb=guide2023&dept=CPSC">CPSC 452</a>.</li>
                                <li>Nice-to-have background (have taken a course or have done research)
                                    <ul>
                                        <li>machine Learning (minimum: high familiarity with linear algebra and multi-variable calculus)</li>
                                        <li>algorithm, probability and statistics</li>
                                    </ul>
                                </li>
                                <li>Programming <ul>
                                        <li>You should be able to write non-trivial programs (in <b>Python</b>), as well
                                            as knowledge about common libaries such as NumPy (<b>Vectorization</b>), Pandas, etc.</li>
                                        <li>Ideally you have used <b>PyTorch</b> (or equivalent) before. But learning it
                                            is not too hard if you have good knowledge in machine learning.</li>
                                    </ul>
                                </li>
                            </ul>
                        </li>
                    </ul>
                </v-sheet>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-sheet class="pa-8" elevation="6">
                    <h1>Readings</h1>
                    <h2>Recommended Readings</h2>
                    <ul>
                        <li>PyTorch <a href="https://pytorch.org/docs/stable/index.html">documentation</a> and <a href="https://pytorch.org/tutorials/">tutorial</a></li>
                        <li>Pre-reading for next lecture will be announced at the end of the previous class</li>
                        <li>Research papers</li>
                    </ul>
                    <h2>Optional Readings</h2>
                    <ul>
                        <li>Please see <a :href="BASE_URL+'#/syllabus'">syllabus</a></li>
                        These will be very useful for course projects.
                    </ul>
                </v-sheet>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-sheet class="pa-8" elevation="6">
                    <h1>Communication</h1>
                    <h2>Ed Discussion</h2>
                    <ul>
                        <li>Sign up <a href="https://edstem.org/us/courses/83811">Ed Discussion</a> with your @yale.edu email.</li>
                        <li>Please participate and help each other, but
                            <ul>
                                <li>Annotate your questions</li>
                                <li>Search for answers before you ask</li>
                                <li>Don't post code</li>
                            </ul>
                        </li>
                        <li><b>We do not encourage private posts on Ed Discussion</b> as they reduce the efficience with which we serve all students.</li>
                    </ul>
                    <h2>Mailing List</h2>
                    <ul>
                        <li>Teaching staff: <a
                                href="mailto:cpsc471_fall25_staff@googlegroups.com">cpsc471_fall25_staff@googlegroups.com</a></li>
                        <ul>
                          <li>Send email to the mailing list if you have requests or questions (not individual instructor / TA).</li>
                          <li>Only email the instructor if the message is highly private / not related to teaching in general.</li>
                        </ul>
                    </ul>

                    <h2>Office Hours</h2>
                    <p>Refer to <a :href="BASE_URL+'#/officehours'">Office Hours</a>.</p>

                    <h3>We will post course annoucements to this website. Make sure you check it regularly. </h3>
                </v-sheet>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
                <v-sheet class="pa-8" elevation="6">
                    <h1>Machine Learning Tools</h1>
                    <ul>
                        <li><a href="https://github.com/pytorch/pytorch">Pytorch</a>
                        </li>
                        <li>There are many libraries for specific architectures:
                            <ul>
                                <li><a href="https://huggingface.co/">Hugging Face</a> is a good place to check out the tools</li>
                                <li>Most papers have associated codebase on <a href="https://github.com/">GitHub</a>, it is recommended to search standard libraries/tools the community is using.</li>
                            </ul>
                        </li>
                        <li>Computational resource from <a href="https://research.computing.yale.edu/">YCRC</a> can be utilized</li>
                        <ul>Information about computation resources will be provided after the proposals are submitted!</ul>
                    </ul>
                </v-sheet>
            </v-col>
        </v-row>
    </v-container>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
    data() {
        return {
            BASE_URL: import.meta.env.BASE_URL
        }
    }
})
</script>
