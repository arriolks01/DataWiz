## Welcome to My Data Science Portfolio!

As promised and discussed over and over. Here it is! As I pursue my journey in self education, 
I will add all my projects here as well as a few projects I worked on during my undergrad as an 
Electrical engineering student with a minor in Computer Information Systems.

Normaldash.jpg


```markdown
## app.R ##
library(shiny)
library(shinydashboard)
install.packages("moments")



ui <- dashboardPage(
  dashboardHeader(),# dashboardHeader
  dashboardSidebar(
    
    sidebarMenu(
      
      menuItem("Uniform Distribution",tabName = "Uniform", icon=icon("square")),#item1
      
      menuItem("Normal Distribution",tabName = "Normal", icon=icon("bell-o")) #item2 
      
    ) #sidebar menu
    
    
  ),#dashboardSidebar
  dashboardBody()#dashboardBody
)#dashboardPage

server <- function(input, output) { }

shinyApp(ui, server)

```


