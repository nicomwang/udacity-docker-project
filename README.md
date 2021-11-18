# udacity-docker-project

### Setting up the project in AWS

1. Create an environment in Cloud9 ( use Amazon Linux, and all other default configurations ). <br>

2. Create a github project.<br>

3. Create a SSH key in Cloud 9<br>

    `ssh-keygen -t rsa `<br>

4. Save the SSH key in your Github.<br>

5. CLone the github project using SSH.<br>

6. `cd <github_project`<br>

7. Create Makefile, Dockerfile, app.py, requirements.txt.<br>

8. Install and use hadolint <br>

   Run the commands in the terminal<br>

    ```
    wget https://github.com/hadolint/hadolint/releases/download/v1.15.0/hadolint-Linux-x86_64
    chmod +x hadolint-Linux-x86_64
    sudo mv hadolint-Linux-x86_64 /usr/local/bin/hadolint

    ```

9. Create a virtual environment<br>

    ` python3 -m venv ~/.udacity-docker-project`<br>

10. Run that virtual environment<br>

    `source ~/.udacity-docker-project/bin/activate`<br>

11. Run `make install` to download all the dependencies specified in the requirements file.<br>

12. Run `docker build --tag=app .` to create the image out of the Dockerfile.

    Run `docker image ls` to see the image just created with the repo name `app`

13. Run `docker run -it app bash` to get into the shell of the container 

14. Config CircleCI

    - `mkdir .circleci`

    - `touch .circleci/config.yml`

    - Edit the config.yml file

15. Run circleCi locally

    - Copy the link for CirleCI-LINUX from https://github.com/CircleCI-Public/circleci-cli/releases
      Go to terminal, type `cd /tmp`
      And then do `wget <copied_link>`
      And then `tar zxvf <name_of_the_file>
      ``cd circleci-cli_0.1.7179_linux_amd64`
      `./circleci`

      this lets you stimulate some commands locally that circleci would do remotely.

    - Let us move this inside our project: `mv circleci ~/environment`

      `(.udacity-docker-project) ec2-user:~/environment $ ls` -> This should list `circleci`, `README.md`,  `udacity-docker-project`.
