

delete all untaget images

   <?bash
       docker image rm $(docker image ls --format "{{.ID}}" --filter "dangling=true")
   ?>
