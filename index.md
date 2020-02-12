## Welcome to My Data Science Portfolio!

As promised and discussed over and over. Here it is! As I pursue my journey in self education, 
I will add all my projects here as well as a few projects I worked on during my undergrad as an 
Electrical engineering student with a minor in Computer Information Systems.

[URL](url) and ![](src)


```markdown


#--------------------------------SERVER-----------------------------------------------------------

`server <- function(input, output) {
  
  histdata <-reactive({runif(input$number,min=0,max=1)})
  densitydata <- reactive({rnorm(input$normnumber)})
  
  output$hist<- renderPlot({
    
    hist(histdata(),xlab="Value",
         
         main=paste(input$number,"random values between 0 and 1"))
  })
  
  output$density<- renderPlot({
    
    hist(densitydata(),xlab="Value",
         
         main=paste("Standard normal distribution\n",input$normnumber,"random values"), probability = TRUE)
    lines(density(densitydata()))
    
  })
    
    #add render Valueboxes here ??
    
    output$meanBox <-renderValueBox({
      
    valueBox(
      
      round (mean(histdata()),3),"Mean",
      color="aqua"
      
      )
    })#output$meanBox <-renderValueBox
    
    output$medianBox <-renderValueBox({
      
      valueBox(
        
        round (median(histdata()),3),"Median",
        color="fuchsia"
        
      )
    })#output$medianBox <-renderValueBox
    
    
    output$sdBox <-renderValueBox({
      
      valueBox(
        
        round (sd(histdata()),3),"Standard deviation",
        color="purple"
        
      )
    })#output$sdBox <-renderValueBox
    
    
    output$meanInfoBox <-renderInfoBox({
      
      infoBox("Mean",
             round(mean(densitydata()),3),
             icon=icon("align-center"),
             color = "aqua")
      })#output$meanInfoBox <-renderInfoBox
    
    
    output$medianInfoBox <-renderInfoBox({
      
      infoBox("Median",
              round(median(densitydata()),3),
              icon=icon("area-chart"),
              color = "fuchsia")
    })#output$medianInfoBox <-renderInfoBox
    
    output$sdInfoBox <-renderInfoBox({
      
      infoBox("Standard Deviation",
              round(sd(densitydata()),3),
              icon=icon("scribd"),fill=FALSE,
              color = "purple")
    })#output$medianInfoBox <-renderInfoBox`
    

  
}#server

shinyApp(ui, server)

```


