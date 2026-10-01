# AWS Serverless SQS Message Processor Workflow

This repository houses an architecture deployment demonstrating a decoupled event-driven data processing pipeline built on Amazon Web Services (AWS).

## 🛠️ Step-by-Step Architecture Configuration

### 1. Ingestion Lane Setup (Amazon SQS)
1. Navigate to the **Amazon SQS Console**.
2. Provision a new **Standard Queue** configured with default settings.
3. Label the queue identifier exactly as: `SQS_TEST_code`.

### 2. Compute Layer Provisioning (AWS Lambda)
1. Navigate to the **AWS Lambda Console** and select **Create Function**.
2. Select the **Use a blueprint** initialization template framework.
3. Filter templates using the text flag `sqs`, choosing the **`hello-world-function-for-sqs`** Node.js architecture preset.
4. Name the runtime compute target: `lambert`.
5. Set the **Execution Role** configuration block to automatically handle basic IAM policy generation permissions.
6. Bind the operational event trigger framework directly to the previously deployed `SQS_TEST_code` queue resource.
7. Click **Create Function** to launch.

## 📐 End-to-End Operational Validation Workflow
To verify integration consistency across the messaging system:
1. Access the `SQS_TEST_code` messaging panel and click **Send and receive messages**.
2. Post an arbitrary validation text string into the body segment execution chamber and click submit.
3. Access the tracking log outputs inside the **Amazon CloudWatch Log Management** console under the specific `/aws/lambda/lambert` workspace streams.
4. Verify structural receipt by validating the decoded output line:
   `INFO SQS message <message-id> : "your test text payload"`
