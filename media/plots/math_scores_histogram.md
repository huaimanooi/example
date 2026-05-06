library(tidyverse)
library(plotly)

p_math_hist <- ggplot(bigclass, aes(x = Math)) +
  geom_histogram(binwidth = 50, fill = '#0072B2', color = 'white') +
  labs(
    title = 'Distribution of Math Scores',
    x = 'Math Score',
    y = 'Frequency'
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white', color = NA),
    axis.title = element_text(size = 18),
    axis.text = element_text(size = 14)
  )

p_math_plotly <- ggplotly(p_math_hist)

# Save as HTML widget
htmlwidgets::saveWidget(
  widget = p_math_plotly,
  file = 'media/plots/math_scores_histogram.html',
  selfcontained = TRUE
)

# To view the plot:
# browseURL('media/plots/math_scores_histogram.html')
