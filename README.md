#include <stdio.h>

// Function to calculate total marks
int calculateTotal(int marks[], int subjects) {
    int total = 0;
    for (int i = 0; i < subjects; i++) {
        total += marks[i];
    }
    return total;
}

// Function to calculate average marks
float calculateAverage(int total, int subjects) {
    return (float)total / subjects;
}

int main() {
    int students = 8;         // Fixed number of students
    int subjects;             // Number of subjects per student

    printf("Enter number of subjects for each student: ");
    scanf("%d", &subjects);

    int marks[students][subjects];
    int totalMarks[students];
    float averageMarks[students];
    float classAverage = 0;

    // Input marks for each student
    for (int i = 0; i < students; i++) {
        printf("\nEnter marks for Student %d:\n", i + 1);
        for (int j = 0; j < subjects; j++) {
            printf("Subject %d: ", j + 1);
            scanf("%d", &marks[i][j]);
        }

        totalMarks[i] = calculateTotal(marks[i], subjects);
        averageMarks[i] = calculateAverage(totalMarks[i], subjects);
        classAverage += averageMarks[i];
    }

    classAverage = classAverage / students;

    // Display results
    printf("\n\n----- Class Performance Report -----\n");
    for (int i = 0; i < students; i++) {
        printf("\nStudent %d:\n", i + 1);
        printf("Total Marks = %d\n", totalMarks[i]);
        printf("Average Marks = %.2f\n", averageMarks[i]);
    }

    // Display overall performance
    printf("\n----- Overall Class Performance -----\n");
    printf("Class Average = %.2f\n", classAverage);

    if (classAverage >= 90)
        printf("Performance: Excellent 💫\n");
    else if (classAverage >= 75)
        printf("Performance: Good 👍\n");
    else if (classAverage >= 50)
        printf("Performance: Average 🙂\n");
    else
        printf("Performance: Needs Improvement 😕\n");

    return 0;
}
# c-programing-marks-calculator
