#### R Console Startup ####
.First <- function() {

  ### Clear Console & Print R Version
  cat('\014')
  cat(paste(R.Version()$version.string,R.Version()$nickname,'\n'))

  ### Load/Install Packages: `pacman`, `formatR`, `rmarkdown`
  require('pacman', quietly = T)
  pacman::p_load(formatR, rmarkdown, install = T)

  ### Open Markdown Script
  setHook('rstudio.sessionInit', function(newSession) {
    if (newSession)
      rstudioapi::navigateToFile('NYPD-Shooting-Incident-Data-Report.Rmd', line = -1L, column = -1L)
  }, action = 'append')
}

#### R Console Close ####
### Clear Console,  Objects in Global Environment, & Clear Graphics
.Last <- function() {

  done<-function(){
    rm(list = setdiff(ls(envir = .GlobalEnv), lsf.str(envir = .GlobalEnv)), envir = .GlobalEnv)
    graphics.off()
    cat('\014')
  }
  done()
}


