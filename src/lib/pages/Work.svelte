<script lang="ts">
  import Card from "$lib/components/Card.svelte";
  import Page from "$lib/components/Page.svelte";
  import { neutralBackground } from "$lib/utils/constants";

  type Job = {
    employer: string;
    title: string;
    startDate: Date;
    endDate: Date;
    tasks: string[];
    tags?: string[];
  };
  const months = [
    "January",
    "February",
    "March",
    "April",
    "May",
    "June",
    "July",
    "August",
    "September",
    "October",
    "November",
    "December",
  ];
  const currentDate = new Date();
  function dateToString(date: Date) {
    return `${months[date.getMonth()]} ${date.getFullYear()}`;
  }
  function formatDateString(start: Date, end: Date) {
    return `${dateToString(start)} - ${dateToString(end) ?? "Present"}`;
  }
  const jobs: Array<Job> = [
    {
      employer: "Summit auto body indudtry Co.,Ltd.",
      title: "Maintenance engineer internship",
      startDate: new Date(2018, 5),
      endDate: new Date(2018,7),
      tasks: [
        "Checking, repairing and servicing machinery, equipment, systems and infrastructures",
        "Ensure that industrial machinery and equipment runs smoothly and reliably",
        "Write a PLC program to set the machine operation.",
      ],
      tags: [
        "Electrical Engineer",
        "Maintenance",
        "PLC",
        "Machines",
      ],
    },
    {
      employer: "OGA company Sriracha branch",
      title: "Internal Technician",
      startDate: new Date(2021, 8),
      endDate: new Date(2022, 1),
      tasks: [
        "Repairing products that sold by company such as Industrial printer, Handheld mobile computer, Industrial scanner, etc.",
        "Checking and Testing product before sell to customer. "
      ],
      tags: ["Electronics", "Technician"],
    },
  ];

  export let backgroundClass = neutralBackground;
</script>

<Page id="work" title="Work Experience" {backgroundClass}>
  <div
    class="container mx-auto grid max-w-screen-xl gap-4 md:grid-cols-1 xl:grid-cols-2 3xl:grid-cols-4"
  >
    {#each jobs as job}
      <Card
        title={job.employer}
        subtitle={`${job.title}, ${formatDateString(
          job.startDate,
          job.endDate
        )}`}
        tags={job.tags}
      >
        <ul class="list-disc list-inside">
          {#each job.tasks as task}
            <li>{task}</li>
          {/each}
        </ul>
      </Card>
    {/each}
  </div>
</Page>
