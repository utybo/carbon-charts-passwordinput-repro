<script lang="ts">
import "carbon-components-svelte/css/g100.css";
  import {
    Header,
    HeaderNav,
    HeaderNavItem,
    HeaderNavMenu,
    SkipToContent,
    Content,
    Grid,
    Row,
    PasswordInput,
    Column,
  } from "carbon-components-svelte";
  import "@carbon/charts/styles-g100.css"
  import { AreaChart } from "@carbon/charts-svelte";

  let isSideNavOpen = false;

  let areaTimeSeriesData = [
	{ group: 'Dataset 1', date: new Date(2019, 0, 1), value: 0 },
	{ group: 'Dataset 1', date: new Date(2019, 0, 6), value: 57312 },
	{ group: 'Dataset 1', date: new Date(2019, 0, 8), value: 21432 },
	{ group: 'Dataset 1', date: new Date(2019, 0, 15), value: 70323 },
	{ group: 'Dataset 1', date: new Date(2019, 0, 19), value: 21300 },
	{ group: 'Dataset 2', date: new Date(2019, 0, 1), value: 50000 },
	{ group: 'Dataset 2', date: new Date(2019, 0, 5), value: 15000 },
	{ group: 'Dataset 2', date: new Date(2019, 0, 8), value: 20000 },
	{ group: 'Dataset 2', date: new Date(2019, 0, 13), value: 39213 },
	{ group: 'Dataset 2', date: new Date(2019, 0, 19), value: 61213 },
	{ group: 'Dataset 3', date: new Date(2019, 0, 2), value: 10 },
	{ group: 'Dataset 3', date: new Date(2019, 0, 6), value: 37312 },
	{ group: 'Dataset 3', date: new Date(2019, 0, 8), value: 51432 },
	{ group: 'Dataset 3', date: new Date(2019, 0, 13), value: 40323 },
	{ group: 'Dataset 3', date: new Date(2019, 0, 19), value: 31300 },
];
const areaTimeSeriesOptions = {
	title: 'Area (time series)',
	axes: {
		bottom: {
			title: '2019 Annual Sales Figures',
			mapsTo: 'date',
			scaleType: 'time',
		},
		left: {
			mapsTo: 'value',
			title: 'Conversion rate',
			scaleType: 'linear',
		},
    curve: "curveNatural",
    height: "400px"
	},
};
</script>

<Header company="IBM" platformName="Carbon Svelte" bind:isSideNavOpen>
  <div slot="skip-to-content">
    <SkipToContent />
  </div>
</Header>

<Content>
  <Grid>
    <Row>
      <Column>
        <PasswordInput labelText="this is a test" placeholder="this is still a test" />
      </Column>
    </Row>
    <Row>
      <Column>
  <AreaChart data={areaTimeSeriesData} options={areaTimeSeriesOptions}/>
      </Column>
    </Row>
  </Grid>
</Content>