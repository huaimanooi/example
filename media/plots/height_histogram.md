library(tidyverse)
library(plotly)

p_height_hist <- ggplot(bigclass, aes(x = height)) +
  geom_histogram(binwidth = 5, fill = '#0072B2', color = 'white') +
  labs(
    title = 'Distribution of Height',
    x = 'Height (inches)',
    y = 'Frequency'
  ) +
  theme_minimal() +
  theme(
    plot.background = element_rect(fill = 'white', color = NA),
    axis.title = element_text(size = 18),
    axis.text = element_text(size = 14)
  )

p_height_plotly <- ggplotly(p_height_hist)

# Save as HTML widget
htmlwidgets::saveWidget(
  widget = p_height_plotly,
  file = 'media/plots/height_histogram.html',
  selfcontained = TRUE
)

# To view the plot:
# browseURL('media/plots/height_histogram.html')
