# GitHub Access Permissions Test

Test GitHub access permissions for the repository: **https://github.com/chadwyatt/ai-voicemail-netlify**

## Objectives

This is a minimal test job to verify that we have the necessary permissions to work with the target repository. Complete the following steps and document what works and what doesn't.

## Tasks

### 1. Clone the Repository
- Clone the repository to a temporary location outside the current working directory
- Use: `git clone https://github.com/chadwyatt/ai-voicemail-netlify.git /tmp/test-repo`
- Document: Success or failure

### 2. Check Read Permissions
- List the root directory contents of the cloned repository
- List any subdirectories (at least 2 levels deep)
- Read and display the first 10 lines of any README or main configuration file
- Document: What files and structure you can see

### 3. Create a Test File
- In the cloned repository, create a file called `test-access.txt` at the root
- Content should include:
  - Current timestamp
  - A message: "GitHub access test by thepopebot"
  - Job ID: 9b387e99-79d8-49a2-a0ff-f47021bc915d
- Document: File creation success

### 4. Attempt to Commit
- Configure git with appropriate credentials (if available via gh CLI)
- Create a new branch named `test/github-access-9b387e99`
- Stage the test file
- Commit with message: "test: verify GitHub access permissions"
- Document: Commit success or failure

### 5. Attempt to Push and Create PR
- Try to push the branch to the remote repository
- If push succeeds, attempt to create a pull request using `gh pr create`
  - Title: "Test: GitHub Access Verification"
  - Body: "Automated test to verify repository access permissions. Job ID: 9b387e99-79d8-49a2-a0ff-f47021bc915d"
- Document: Push and PR creation results

## Final Report

Create a summary report in this job.md file (append to the end) that includes:

1. **Read Access**: ✅ or ❌ with details
2. **Write Access**: ✅ or ❌ with details  
3. **Branch Creation**: ✅ or ❌ with details
4. **Push Access**: ✅ or ❌ with details
5. **PR Creation**: ✅ or ❌ with details
6. **Overall Assessment**: What can we do with this repository?
7. **Recommendations**: Any additional permissions needed for future work

## Notes

- This test is performed in `/tmp/test-repo` to keep it separate from the current working directory
- If any step fails, document the error message and continue to the next step where possible
- The goal is to understand the full scope of our access, not to succeed at everything
