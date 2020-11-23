

# libraries ==========================
library(ggplot2)
library(dplyr)
library(lubridate)

# data ===============================

# brady
data.strava.bn <- as.data.frame(read.csv("activities_20200516.csv", header=TRUE, sep=","))
data.strava.bn$Distance.mi <- data.strava.bn$Distance / 1.60934
data.strava.bn$Elev.Gain.ft <- data.strava.bn$Elevation.Gain * 3.2808
# data.strava.bn$Yr <- year(data.strava.bn$Activity.Date)
# data.strava.bn$Elapsed.Time.m <- data.strava.bn$Elapsed.Time.s / 60
# data.strava.bn$Pace.mi.per.min <- data.strava.bn$Distance.mi / data.strava.bn$Elapsed.Time.m
# data.strava.bn$Pace.min.per.mi <- 1 / data.strava.bn$Pace.mi.per.min
# data.strava.bn$user <- c(rep("bn", 1))

data.runs.bn <- data.strava.bn %>%
  filter(Activity.Type == "Run")

# data.runs <- rbind(data.runs.bn, data.runs.jr)

runs.hist <- ggplot(data.runs.bn, aes(x=Distance.mi))+
  geom_histogram(binwidth = 1, alpha=0.5, position="identity")
runs.hist

runs.hist <- ggplot(data.runs.bn, aes(x=Elev.Gain.ft))+
  geom_histogram(binwidth = 100, alpha=0.5, position="identity")
runs.hist

runs.scatter <- ggplot(data.runs.bn, aes(x = Distance.mi, y = Moving.Time))+
  geom_point()
runs.scatter

runs.scatter <- ggplot(data.runs.bn, aes(x = Distance.mi, y = Max.Grade))+
  geom_point()
runs.scatter

runs.scatter <- ggplot(data.runs.bn, aes(x = Distance.mi, y = Calories, color=Athlete.Weight))+
  geom_point()
runs.scatter

runs.scatter <- ggplot(data.runs.bn, aes(x = Distance.mi, y = Average.Speed))+
  geom_point()
runs.scatter

runs.scatter <- ggplot(data.runs.bn, aes(x = Elevation.Gain, y = Average.Speed))+
  geom_point()
runs.scatter

runs.scatter <- ggplot(data.runs.bn, aes(x = Average.Cadence, y = Average.Speed))+
  geom_point()
runs.scatter






# jessica
data.strava.jr <- as.data.frame(read.csv("activities_jr.csv", header=TRUE, sep=","))
data.strava.jr$Distance.mi <- data.strava.jr$Distance.km / 1.60934
data.strava.jr$Elapsed.Time.m <- data.strava.jr$Elapsed.Time.s / 60
data.strava.jr$Pace.mi.per.min <- data.strava.jr$Distance.mi / data.strava.jr$Elapsed.Time.m
data.strava.jr$Pace.min.per.mi <- 1 / data.strava.jr$Pace.mi.per.min
data.strava.jr$user <- c(rep("jr", 1))


data.runs.jr <- data.strava.jr %>%
  filter(Activity.Type == "Run" & Pace.min.per.mi <15)

