# JMeter Performance Testing – Manan Application

This repository contains a JMeter performance testing project for the Manan application. https://manan.numpyninja.com/
The goal is to simulate concurrent user load, monitor API performance, and generate HTML reports automatically using GitHub Actions CI/CD.

## Test Plan Details

Test Tool: Apache JMeter 5.6.3

Application Under Test (AUT): https://manan.numpyninja.com

Test Plan: manan_api_test.jmx

Test Data: data.csv (defines number of users)

User Load: Simulated 36 users (from CSV)

Samplers Used:

HTTP Request Samplers for API endpoints

CSV Data Set Config for parameterization

Assertions to validate responses

## Running Tests Locally
1. Install JMeter

Download and extract JMeter from Apache JMeter.

2. Run Test Plan
jmeter -n -t test-plans/manan_api_test.jmx -l results/results.jtl -e -o results/html-report


-n → non-GUI mode

-t → JMX test plan

-l → log results to JTL file

-e -o → generate HTML dashboard report

3. View Report

Open results/html-report/index.html in a browser.

## CI/CD with GitHub Actions

This project uses GitHub Actions to automatically run performance tests on every push to the main branch or manual trigger.

Workflow: jmeter.yml

Key steps:

1. Checkout repository

2. Set up Java (Temurin 17)

3. Download and extract JMeter

4. Run JMeter test in non-GUI mode

5. Upload HTML report as pipeline artifact

## Reports

JTL Raw Results → results/results.jtl

HTML Report → results/html-report/

In GitHub Actions → Check Artifacts to download the HTML Report.

## How to Reproduce

Fork/clone this repo

Update data.csv for desired user load

Modify manan_api_test.jmx for your API endpoints

Commit & push → GitHub Actions will run tests automatically

## Report Screenshots


<img width="1905" height="1015" alt="image" src="https://github.com/user-attachments/assets/63b164ce-3339-4a05-8432-199f6278ba76" />


<img width="1899" height="1015" alt="image" src="https://github.com/user-attachments/assets/930259a6-b9a0-4664-bdb2-b679571b571d" />

<img width="1918" height="1014" alt="image" src="https://github.com/user-attachments/assets/5658e2ed-8bf9-43f0-b38d-056e3f5f3392" />

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/6d377691-cde2-4796-9e76-c7a8e73d6990" />



