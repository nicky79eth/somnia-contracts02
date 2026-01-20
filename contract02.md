async function main() {
  const Counter = await ethers.getContractFactory("SomniaCounter");
  const counter = await Counter.deploy();

  await counter.waitForDeployment();
  console.log("SomniaCounter deployed to:", await counter.getAddress());
}

main().catch((error) => {
  console.error(error);
  process.exitCode = 1;
});
