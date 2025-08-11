<script>
	import { onMount } from 'svelte';
	import { Mail, MapPin, Globe, Github, Linkedin, Twitter, ExternalLink, Calendar, Building, GraduationCap, Award, Code, Smartphone, Database, Globe as GlobeIcon } from 'lucide-svelte';

	// Portfolio data
	const profile = {
		name: "Ishan Vohra",
		title: "Software Engineer & Mobile Developer",
		email: "ishanvohra2@gmail.com",
		location: "Delhi, IN",
		website: "ishanvohra2.github.io",
		description: "Passionate software engineer with expertise in mobile development, specializing in React Native, Android, and cross-platform solutions. Currently working at Tether on cutting-edge AI applications with peer-to-peer architecture."
	};

	const education = [
		{
			institution: "Birla Institute of Technology and Science",
			degree: "M.Tech in Software Engineering",
			period: "Aug 2023 - Jul 2025",
			gpa: "8.1/10",
			location: "Pilani, IN"
		},
		{
			institution: "Maharaja Surajmal Institute of Technology, GGSIPU",
			degree: "B.E./B.Tech in Information Technology",
			period: "Aug 2018 - Jul 2022",
			gpa: "8.7/10",
			location: "Delhi, IN"
		}
	];

	const experience = [
		{
			company: "Tether",
			position: "Mobile Engineer",
			period: "Feb 2025 - Present",
			location: "Remote",
			description: "Work on react native applications integrating cutting edge AI libraries combined with Holepunch's peer to peer decentralised architecture."
		},
		{
			company: "Powr of You Ltd (DBA PY Insights)",
			position: "Software Engineer",
			period: "Sept 2022 - Feb 2025",
			location: "Remote",
			description: "Work on different products built for Android OS with varying feature-sets catering to wide variety of userbases and clients. Create backend services and manage resources on AWS that support the functioning of all products."
		},
		{
			company: "Skylark Drones",
			position: "Android Engineer",
			period: "Feb 2022 - Sept 2022",
			location: "Bangalore, IN",
			description: "Develop the Drone Mission Ops (DMO) Pilot application allowing pilots to execute missions seamlessly using their DJI drones."
		},
		{
			company: "Hypd Marketing Technologies Pvt. Ltd.",
			position: "SDE 1",
			period: "Mar 2021 - Feb 2022",
			location: "Delhi, IN",
			description: "Responsible for the development of Hypd's android application. Implemented features such as snackable videos called pebbles, express checkout, live streaming/broadcasting and the e-Commerce flow."
		}
	];

	const projects = [
		{
			name: "Local AI - Offline LLM Chatbot",
			description: "An application which functions as an alternative to ChatGPT by deploying Gemma LLM model locally on the user's device providing an offline first and safe chatbot experience. Local AI has 3,000 active monthly users and almost 15,000 downloads on Google Play store.",
			technologies: ["React native", "Expo", "Javascript", "Peer-to-peer architecture"],
			url: null
		},
		{
			name: "Watcher (Project Super)",
			description: "An application built using Jetpack compose for android that uses Marvel Developer API to provide user a platform to connect with their favorite comic books and characters. The app also uses Spotify SDK to connect to user's spotify account and play a premade playlist creating an immersive user experience.",
			technologies: ["Kotlin", "Jetpack Compose", "MVI"],
			url: "https://play.google.com/store/apps/details?id=com.ishanvohra2.ps"
		}
	];

	const skills = [
		{
			category: "Programming Languages",
			skills: ["Java", "Javascript", "Python", "Kotlin"]
		},
		{
			category: "Cross Platform Development",
			skills: ["Kotlin multiplatform", "React native"]
		},
		{
			category: "Native Development",
			skills: ["Kotlin/Java for Android"]
		},
		{
			category: "Database Management",
			skills: ["SQLite", "SQL", "NoSQL(Firebase cloudstore, AWS DynamoDB)"]
		}
	];

	const awards = [
		{
			title: "Microsoft Learn Student Ambassador - Beta",
			organization: "Microsoft",
			date: "Jan 2020",
			description: "Participated and organized in community events on new tech"
		},
		{
			title: "Smart India Hackathon Winner - Software Edition",
			organization: "Ministry of Education (Govt. of India)",
			date: "Sept 2020",
			description: "National level hackathon organized by the Gov. of India to promote student innovation"
		}
	];

	let currentSection = '';

	onMount(() => {
		// Intersection Observer for section highlighting and animations
		const observer = new IntersectionObserver((entries) => {
			entries.forEach(entry => {
				if (entry.isIntersecting) {
					currentSection = entry.target.id;
					entry.target.classList.add('visible');
				}
			});
		}, { threshold: 0.1 });

		// Observe all sections
		document.querySelectorAll('section[id]').forEach(section => {
			observer.observe(section);
		});

		// Add parallax effect to hero section
		const handleScroll = () => {
			const scrolled = window.pageYOffset;
			const hero = document.querySelector('.hero');
			if (hero) {
				hero.style.transform = `translateY(${scrolled * 0.5}px)`;
			}
		};

		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});
</script>

<svelte:head>
	<title>{profile.name} - {profile.title}</title>
	<meta name="description" content={profile.description} />
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
</svelte:head>

<!-- Navigation -->
<nav class="nav">
	<div class="container nav-container">
		<a href="#home" class="nav-logo">{profile.name}</a>
		<ul class="nav-links">
			<li><a href="#about" class="nav-link">About</a></li>
			<li><a href="#experience" class="nav-link">Experience</a></li>
			<li><a href="#projects" class="nav-link">Projects</a></li>
			<li><a href="#skills" class="nav-link">Skills</a></li>
			<li><a href="#contact" class="nav-link">Contact</a></li>
		</ul>
	</div>
</nav>

<!-- Hero Section -->
<section id="home" class="hero">
	<div class="container">
		<div class="hero-content fade-in-up">
			<h1 class="hero-title">Hi, I'm {profile.name}</h1>
			<p class="hero-subtitle">{profile.description}</p>
			<div class="hero-buttons">
				<a href="#projects" class="btn btn-primary">
					<Code size={20} />
					View My Work
				</a>
				<a href="#contact" class="btn btn-secondary">
					<Mail size={20} />
					Get In Touch
				</a>
			</div>
		</div>
	</div>
</section>

<!-- About Section -->
<section id="about" class="section">
	<div class="container">
		<h2 class="section-title">About Me</h2>
		<div class="grid grid-2">
			<div class="card">
				<h3>Background</h3>
				<p>I'm a passionate software engineer with a strong foundation in mobile development and cross-platform solutions. Currently pursuing my M.Tech in Software Engineering at BITS Pilani, I bring over 4 years of experience in developing innovative mobile applications and backend services.</p>
				<p>My expertise spans across React Native, Android development with Kotlin/Java, and cloud services on AWS. I'm particularly interested in AI integration and peer-to-peer architectures, which I'm currently exploring at Tether.</p>
			</div>
			<div class="card">
				<h3>Education</h3>
				{#each education as edu}
					<div class="mb-4">
						<div class="flex items-center gap-4 mb-2">
							<GraduationCap size={20} color="var(--primary-color)" />
							<div>
								<h4>{edu.institution}</h4>
								<p class="text-secondary">{edu.degree}</p>
								<p class="text-secondary">{edu.period} • {edu.location}</p>
								<p class="text-secondary">GPA: {edu.gpa}</p>
							</div>
						</div>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>

<!-- Experience Section -->
<section id="experience" class="section">
	<div class="container">
		<h2 class="section-title">Work Experience</h2>
		<div class="timeline">
			{#each experience as exp, index}
				<div class="timeline-item">
					<div class="timeline-dot"></div>
					<div class="timeline-content">
						<div class="flex items-center gap-4 mb-2">
							<Building size={20} color="var(--primary-color)" />
							<div>
								<h3>{exp.position}</h3>
								<h4>{exp.company}</h4>
								<div class="flex items-center gap-4 text-secondary">
									<div class="flex items-center gap-1">
										<Calendar size={16} />
										{exp.period}
									</div>
									<div class="flex items-center gap-1">
										<MapPin size={16} />
										{exp.location}
									</div>
								</div>
							</div>
						</div>
						<p>{exp.description}</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Projects Section -->
<section id="projects" class="section">
	<div class="container">
		<h2 class="section-title">Featured Projects</h2>
		<div class="grid grid-2">
			{#each projects as project}
				<div class="project-card">
					<div class="project-content">
						<div class="flex items-center justify-between mb-2">
							<h3 class="project-title">{project.name}</h3>
							{#if project.url}
								<a href={project.url} target="_blank" rel="noopener noreferrer" class="btn btn-secondary" style="padding: 0.25rem 0.5rem; font-size: 0.875rem;">
									<ExternalLink size={16} />
								</a>
							{/if}
						</div>
						<p class="project-description">{project.description}</p>
						<div class="project-tech">
							{#each project.technologies as tech}
								<span class="tech-tag">{tech}</span>
							{/each}
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Skills Section -->
<section id="skills" class="section">
	<div class="container">
		<h2 class="section-title">Skills & Technologies</h2>
		<div class="skills-grid">
			{#each skills as skillCategory}
				<div class="skill-category">
					<h4>{skillCategory.category}</h4>
					<div class="skill-tags">
						{#each skillCategory.skills as skill}
							<span class="skill-tag">{skill}</span>
						{/each}
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Awards Section -->
<section id="awards" class="section">
	<div class="container">
		<h2 class="section-title">Awards & Recognition</h2>
		<div class="grid grid-2">
			{#each awards as award}
				<div class="card">
					<div class="flex items-center gap-4 mb-2">
						<Award size={24} color="var(--primary-color)" />
						<div>
							<h3>{award.title}</h3>
							<p class="text-secondary">{award.organization}</p>
							<p class="text-secondary">{award.date}</p>
						</div>
					</div>
					<p>{award.description}</p>
				</div>
			{/each}
		</div>
	</div>
</section>

<!-- Contact Section -->
<section id="contact" class="section">
	<div class="container">
		<h2 class="section-title">Get In Touch</h2>
		<div class="contact-info">
			<a href="mailto:{profile.email}" class="contact-item">
				<Mail class="contact-icon" />
				<div>
					<h4>Email</h4>
					<p>{profile.email}</p>
				</div>
			</a>
			<div class="contact-item">
				<MapPin class="contact-icon" />
				<div>
					<h4>Location</h4>
					<p>{profile.location}</p>
				</div>
			</div>
			<a href="https://{profile.website}" target="_blank" rel="noopener noreferrer" class="contact-item">
				<Globe class="contact-icon" />
				<div>
					<h4>Website</h4>
					<p>{profile.website}</p>
				</div>
			</a>
		</div>
		<div class="text-center mt-4">
			<p>I'm always open to discussing new opportunities and interesting projects.</p>
			<div class="flex justify-center gap-4 mt-4">
				<a href="mailto:{profile.email}" class="btn btn-primary">
					<Mail size={20} />
					Send Email
				</a>
			</div>
		</div>
	</div>
</section>

<!-- Footer -->
<footer class="footer">
	<div class="container">
		<p>&copy; 2024 {profile.name}. All rights reserved.</p>
		<p>Built with Svelte & ❤️</p>
	</div>
</footer>
