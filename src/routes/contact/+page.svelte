<script lang="ts">
  import type { PageData } from './$types';
  import { superForm } from 'sveltekit-superforms/client';
  import { toastStore, Avatar } from '@skeletonlabs/skeleton';
  import spinner from '$lib/Assets/spinner.svg';

  export let data: PageData;

  let selectedService: Service = "Web Design";

  const { form, errors, constraints, enhance, delayed, tainted } = superForm(data.form, {
      clearOnSubmit: 'errors-and-message',
      multipleSubmits: 'prevent',
      onUpdated({ form }) {
          if (form.valid) {
              // Create a toast
              const t = {
                  message: 'Form submitted successfully!',
                  timeout: 5000,
                  background: 'variant-filled-success',
                  classes: 'unstyled font-sans'
              };
              toastStore.trigger(t); // trigger the toast

              // Clear the form
              $form = {
                  name: '',
                  email: '',
                  company_name: '',
                  title: '',
                  service: 'Web Design',
                  sub_service: services['Web Design'][0], // Set to the first sub_service of 'Web Design'
                  message: '',
              };

              // Update the selectedService variable to 'Web Design'
              selectedService = 'Web Design';

              // Untaint the form
              $tainted = {};
          }
      }
  });

  type Service = "Web Design" | "Web Applications with JS" | "Relational Database";

  const services: Record<Service, string[]> = {
      "Web Design": ["All phases", "Planning", "Design and Prototyping", "Development", "Maintenance and Support"],
      "Web Applications with JS": ["Design & Prototyping", "Front & Back-End Development", "Testing & Deployment", "Maintenance & Support"],
      "Relational Database": ["All phases", "Design and Development","Assessment & Analysis", "Visualizations", "Model Development", "Training and Support"]
  };
  let allSubServices: string[] = [];
  Object.values(services).forEach(subServices => {
      allSubServices = [...allSubServices, ...subServices];
  });
</script>

<svelte:head>
  <title>Matthew Young - Contact</title>
</svelte:head>

<div class="w-screen p-4 lg:p-8 space-y-3">

  <div class="card mx-auto p-10 grid grid-cols-1 md:grid-cols-[auto_1fr_auto] gap-4 md:gap-10 items-center text-center md:text-left max-w-sm md:max-w-[1000px]">
      <div>
        <a href="https://www.linkedin.com/in/jmatty123/" >
            <Avatar
            cursor="cursor-pointer"
            src="https://media.licdn.com/dms/image/D4E03AQF2w8D3R9HUfg/profile-displayphoto-shrink_800_800/0/1684272249639?e=1691020800&v=beta&t=JhaTiP6FfjBy3X3Tkar-q_acBEziyemUMEy1n5P69IQ"
            initials="MY"
            width="w-44"
            class="border-2 border-surface-200-700-token hover:scale-110 duration-100 shadow-lg"
            rounded="rounded-full" 
            />
        </a>
      </div>
      <div class="space-y-4">
          <h3 class="font-thin text-xl">Matthew Young</h3>
          <p class="unstyled font-thin text-base">Aspiring developer and artist with several certifications across fields such as responsive web design, javascript, and relational database design / administration. His passion for the creative process drives him to create novel and effective solutions.</p>
      </div>
      <div class="md:text-center space-y-8">
          <div class="space-y-2">
              <span class="block font-thin text-4xl">$10000 / hr</span>
              <span class="block unstyled font-thin text-sm opacity-75">Minimum 10 hours</span>
          </div>
      </div>
  </div>

  <form method="POST" use:enhance class="card variant-glass p-10 space-y-5 max-w-sm md:max-w-[1000px] mx-auto">
      <fieldset class="grid grid-cols-1 md:grid-cols-2 gap-4">
          <label class="label" for="name">
              <span class="unstyled font-thin">Full Name</span>
              <input id="name" class="input unstyled font-thin text-sm rounded-md py-2 px-3" type="text" name="name" placeholder="Soren Kierkegaard" autocomplete="name" aria-invalid={$errors.name ? 'true' : undefined} bind:value={$form.name} {...$constraints.name} required>
          </label>
          <label class="label" for="email">
              <span class="unstyled font-thin">Email</span>
              <input id="email" class="input unstyled font-thin text-sm rounded-md py-2 px-3" type="email" name="email" placeholder="kierkegaard@either.or" autocomplete="email" aria-invalid={$errors.email ? 'true' : undefined} bind:value={$form.email} {...$constraints.email} required>
          </label>
          <label class="label" for="company_name">
              <span class="unstyled font-thin">Company Name</span>
              <input id="company_name" class="input unstyled font-thin text-sm rounded-md py-2 px-3" type="text" name="company_name" placeholder="Copenhagen University" aria-invalid={$errors.company_name ? 'true' : undefined} bind:value={$form.company_name} {...$constraints.company_name} required>
          </label>
          <label class="label" for="title">
              <span class="unstyled font-thin">Title</span>
              <input id="title" class="input unstyled font-thin text-sm rounded-md py-2 px-3" type="text" name="title" placeholder="Philosopher, Poet, Social Critic" aria-invalid={$errors.title ? 'true' : undefined} bind:value={$form.title} {...$constraints.title} required>
          </label>
          <label class="label" for="service">
              <span class="unstyled font-thin">Service</span>
              <select id="service" class="select unstyled font-thin text-sm rounded-md" name="service" aria-invalid={$errors.service ? 'true' : undefined} bind:value={selectedService} {...$constraints.service} required>
                  <option value="Web Design">Web Design</option>
                  <option value="Web Applications with JS">Web Applications with JS</option>
                  <option value="Relational Database">Relational Database</option>
              </select>
          </label>

          <label class="label" for="sub_service">
              <span class="unstyled font-thin">Sub-service</span>
              <select id="sub_service" class="select unstyled font-thin text-sm rounded-md" name="sub_service" aria-invalid={$errors.sub_service ? 'true' : undefined} bind:value={$form.sub_service} {...$constraints.sub_service} required>
                  {#each services[selectedService] as sub_service (sub_service)}
                      <option value={sub_service}>{sub_service}</option>
                  {/each}
              </select>
          </label>
      </fieldset>
      <fieldset class="grid grid-cols-1 gap-4">
          <label class="label col-span-2" for="message">
              <span class="unstyled font-thin">Message</span>
              <textarea id="message" class="textarea unstyled font-thin text-sm rounded-md py-2 px-3" name="message" rows="4" placeholder="Let me know how I can help!" aria-invalid={$errors.message ? 'true' : undefined} bind:value={$form.message} {...$constraints.message} required></textarea>
          </label>
      </fieldset>
      <fieldset class="flex justify-between items-center gap-4">
          <p class="opacity-50 unstyled font-sans text-sm">I will typically contact you within 24-48 hours.</p>
          <div class="flex items-center gap-x-3">
              <button type="submit" class="btn variant-filled-primary unstyled font-sans text-sm font-bold rounded-md">Submit</button>
              {#if $delayed}<img src={spinner} alt='spinner'/>{/if}
          </div>
      </fieldset>
  </form>
</div>