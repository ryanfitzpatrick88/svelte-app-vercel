<script>
	import { mdiArrowCollapseUp, mdiInformation } from '@mdi/js';

	import { Card, Col, Container, Divider, Icon, Row } from 'svelte-materialify';
</script>

<h1>Dashboard</h1>

<Card style="padding:5px;background-color:#0d47a1;">
	<Row style="padding-left:15px;color:#ffff;">
		<Icon path={mdiInformation} />
		<p style="margin:5px;">For more information head over here!</p>
	</Row>
</Card>
<Divider />
<Container>
	<Row>
		<Col>
			<Card>
				<Row style="padding:20px;"><span> Total Clients</span></Row>
			</Card>
		</Col>
		<Col>
			<Card style="padding:20px;"><span>Total Sales</span></Card>
		</Col>
		<Col>
			<Card style="padding:20px;">
				<span>New Sales</span>
			</Card>
		</Col>
		<Col>
			<Card style="padding:20px;">
				<span>Pending Contracts</span>
			</Card>
		</Col>
	</Row>
</Container>

<!-- 
COLOR SCHEME
P
#0d47a1

P — Light
#5472d3

P — Dark
#002171
 -->
<style>
	@font-face {
		font-family: 'Gelasio';
		font-style: normal;
		font-weight: 400;
		src: local('Gelasio Regular'), local('Gelasio-Regular'),
			url(https://fonts.gstatic.com/s/gelasio/v1/cIf9MaFfvUQxTTqS9C6hYQ.woff2) format('woff2');
	}
	h1 {
		font-family: Gelasio;
	}
	p {
		font-family: Gelasio;
	}
	span {
		font-family: Gelasio;
	}
</style>
