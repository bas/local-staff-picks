# Staff picks

Simple static web app using react and nextjs that shows a list of staff recommended books.

Clone the project and then in the project directory, you can run:

```
npm install
npm run dev
```

Go to http://localhost:3000/ in your browser to visit the web app. You should see a page like this:

<img width="1074" alt="Screenshot 2022-12-18 at 12 20 57" src="https://user-images.githubusercontent.com/1982588/208295564-d9c7890f-3911-40f9-b994-27a7b528e00d.png">

For LaunchDarkly to work you need to add a `.env` file with the following:

```
LAUNCHDARKLY_CLIENT_ID=<Your Client ID>
```

## Terraform

Use the Terraform CLI to provision the project in your LaunchDarkly account:

```
terraform init
terraform validate
terraform apply -var="LAUNCHDARKLY_ACCESS_TOKEN=your_access_token" -var="project=your_project_name" -auto-approve
```

Make sure to pass the folowing variables:

- LAUNCHDARKLY_ACCESS_TOKEN
- project

## Docker

To run in Docker, first build the image:

```
docker build -t staff-picks .
```

Then run the image using the following command:

```
docker run --name staff-picks -p 3000:3000 staff-picks
```

To stop the container:

```
docker stop staff-picks
```

To remove the container:

```
docker rm staff-picks
```

To remove the image:

```
docker rmi staff-picks
```

Check the [Terraform module](terraform/main.tf) for the flags used in this project.
