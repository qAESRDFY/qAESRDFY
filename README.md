import matplotlib.pyplot as plt
import seaborn as sns

# Hypothetical data
schools = ['West Grove', 'St. Andrew\'s', 'Wolfson Hillel']
survey_scores = [20, 18, 25]
ofsted_ratings = ['Good', 'Good', 'Outstanding']

# Scatterplot with regression line
plt.figure(figsize=(10, 6))
sns.regplot(x=survey_scores, y=range(len(schools)), ci=None, line_kws={'color': 'red'})

# Scatterplot points
plt.scatter(survey_scores, range(len(schools)), color='blue', s=100)

# Annotating each point with school name and Ofsted rating
for i, txt in enumerate(schools):
    plt.annotate(f'{txt}\nOfsted: {ofsted_ratings[i]}', (survey_scores[i], i), fontsize=10, ha='right')

# Plot details
plt.title('Correlation Between Parent Survey Scores and Ofsted Ratings')
plt.xlabel('Parent Survey Scores')
plt.yticks(range(len(schools)), schools)
plt.ylabel('Schools')
plt.grid(True)
plt.show()

