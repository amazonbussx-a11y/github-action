const core = require('@actions/core');

async function run() {
  try {
    const name = core.getInput('name') || 'World';
    const repoName = core.getInput('repo-name') || process.env.GITHUB_REPOSITORY || 'unknown-repo';

    const message = `Hello ${name}! This action ran in ${repoName}.`;

    core.setOutput('greeting', message);
    core.info(message);    console.log(message);
  } catch (error) {
    core.setFailed(error.message);
  }
}

run();