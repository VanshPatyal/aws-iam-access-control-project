# IAM Implementation Steps

## Step 1: Analyze Current IAM Setup
1. Log in to AWS Console
2. Navigate to IAM Dashboard
3. Review existing users, groups, and policies
4. Document current permission boundaries

## Step 2: Create IAM Groups
1. Go to IAM → User Groups → Create Group
2. Create group: `S3-Support`
3. Create group: `EC2-Support`
4. Create group: `EC2-Admin`

## Step 3: Attach Policies to Groups
### S3-Support Group
- Attach custom policy: `s3-support-policy.json`
- Permissions: Read-only S3 access

### EC2-Support Group
- Attach custom policy: `ec2-support-policy.json`
- Permissions: Read-only EC2 access

### EC2-Admin Group
- Attach custom policy: `ec2-admin-policy.json`
- Permissions: Full EC2 access

## Step 4: Create Users and Assign to Groups
1. Create test users:
   - `s3-support-user`
   - `ec2-support-user`
   - `ec2-admin-user`
2. Assign each user to respective group
3. Generate console passwords for testing

## Step 5: Test Permissions
### Test S3 Support User
- [ ] Sign in as s3-support-user
- [ ] Try to list S3 buckets → Should succeed
- [ ] Try to download file → Should succeed
- [ ] Try to delete file → Should FAIL

### Test EC2 Support User
- [ ] Sign in as ec2-support-user
- [ ] Try to list EC2 instances → Should succeed
- [ ] Try to view security groups → Should succeed
- [ ] Try to stop an instance → Should FAIL

### Test EC2 Admin User
- [ ] Sign in as ec2-admin-user
- [ ] Try to list instances → Should succeed
- [ ] Try to stop an instance → Should succeed
- [ ] Try to terminate an instance → Should succeed

## Step 6: Monitor with CloudTrail
1. Go to CloudTrail → Event history
2. Filter by username to verify actions
3. Confirm that only allowed actions appear

## Step 7: Documentation & Handoff
1. Document all group policies
2. Create user login instructions
3. Provide testing results summary
