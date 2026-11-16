function dailyLog233() {
  const builds = [
    { status: "success", duration: 42 },
    { status: "failed", duration: 35 },
    { status: "success", duration: 48 },
    { status: "success", duration: 39 },
    { status: "failed", duration: 51 },
    { status: "success", duration: 44 }
  ];

  const total = builds.length;
  const successful = builds.filter(
    build => build.status === "success"
  ).length;

  const failed = total - successful;

  const averageDuration = builds.reduce(
    (sum, build) => sum + build.duration,
    0
  ) / total;

  console.log("Daily Build Report");
  console.log("------------------");
  console.log(`Total Builds: ${total}`);
  console.log(`Successful: ${successful}`);
  console.log(`Failed: ${failed}`);
  console.log(`Success Rate: ${(successful / total * 100).toFixed(1)}%`);
  console.log(`Average Duration: ${averageDuration.toFixed(1)} seconds`);
}

dailyLog233();
