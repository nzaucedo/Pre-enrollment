<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bachelor's Degree in Architecture - Pre-enrollment</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css">
    <style>
        body {
            background-color: #f5f8fa;
            color: #003366;
            font-family: Arial, sans-serif;
        }
        .container {
            margin-top: 30px;
        }
        .credit-warning {
            color: red;
            font-weight: bold;
            display: none;
        }
        .course-section {
            margin-bottom: 20px;
        }
        .course-title {
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 class="text-center">Pre-enrollment Form</h1>
        <form id="preEnrollmentForm">
            <div class="mb-3">
                <label for="name" class="form-label">Full Name</label>
                <input type="text" id="name" name="name" class="form-control" required>
            </div>

            <div class="mb-3">
                <label for="email" class="form-label">Email (must end with @uic.es)</label>
                <input type="email" id="email" name="email" class="form-control" pattern="^[a-zA-Z0-9._%+-]+@uic\.es$" required>
                <div class="invalid-feedback">Email must end with @uic.es</div>
            </div>

            <h3>Enrollment Type</h3>
            <div class="mb-3">
                <select id="enrollmentType" class="form-select" required>
                    <option value="">Select Enrollment Type</option>
                    <option value="half">Half-time Enrollment (min. 30, max. 36 credits)</option>
                    <option value="full">Full Enrollment (min. 60, max. 72 credits)</option>
                </select>
            </div>

            <h3>Subjects Selection</h3>
            <p><strong> Important:</strong> Respect the credit limits for your enrollment.</strong>
              <p><strong>  Also please Take note:</strong> A) To enroll in Urban Design II, you must have passed Urban Design I. 
                B) To enroll in Building Construction III, you must have passed; Introduction to Arch.Construction, Building Construction I, and II. 
                C) To enroll in Design Studio V, you must have passed all previous Design Studio courses.
 <p><strong> Please, in case you are taking subjects from different courses;</strong> check that the selected subjects do not have timetable overlaps.</p>

            <div id="subjects">
                <!-- Dynamic subjects list grouped by course -->
            </div>

            <div class="mt-3">
                <label for="totalCredits" class="form-label">Total Selected Credits</label>
                <input type="text" id="totalCredits" class="form-control" readonly>
            </div>

            <div id="creditWarning" class="credit-warning">
                Credit total must match the limits of your selected enrollment type.
            </div>

            <div class="mt-3 d-none" id="justificationDiv">
                <label for="justification" class="form-label">Justification (for half-time enrollment)</label>
                <textarea id="justification" class="form-control"></textarea>
            </div>

            <h3>Discount Options</h3>
            <div class="form-check">
                <input type="checkbox" id="generalLargeFamily" name="discount" class="form-check-input">
                <label class="form-check-label" for="generalLargeFamily">General Large Family (attach photo of valid card)</label>
                <input type="file" class="form-control mt-2">
            </div>

            <div class="form-check">
                <input type="checkbox" id="specialLargeFamily" name="discount" class="form-check-input">
                <label class="form-check-label" for="specialLargeFamily">Special Large Family (attach photo of valid card)</label>
                <input type="file" class="form-control mt-2">
            </div>

           <div class="form-check">
    <input type="checkbox" id="scholarshipBEA" name="discount" class="form-check-input">
    <label class="form-check-label" for="scholarshipBEA">Scholarship BEA</label>
    <input type="number" id="beaPercentage" class="form-control mt-2 d-none" placeholder="%" min="0" max="100">
</div>

<script>
    // Escucha el cambio de estado del checkbox
    document.getElementById('scholarshipBEA').addEventListener('change', function () {
        const percentageInput = document.getElementById('beaPercentage');
        if (this.checked) {
            // Muestra el cuadro de porcentaje si el checkbox está marcado
            percentageInput.classList.remove('d-none');
        } else {
            // Oculta el cuadro de porcentaje si el checkbox está desmarcado
            percentageInput.classList.add('d-none');
        }
    });
</script>

            <div class="form-check">
                <input type="checkbox" id="internationalExcellence" name="discount" class="form-check-input">
                <label class="form-check-label" for="internationalExcellence">International Excellence</label>
            </div>

         <div class="form-check">
    <input type="checkbox" id="otherDiscount" name="discount" class="form-check-input">
    <label class="form-check-label" for="otherDiscount">Other</label>
    <textarea id="otherDiscountDetails" class="form-control mt-2 d-none" placeholder="Provide details"></textarea>
</div>

<script>
    // Escucha el cambio de estado del checkbox
    document.getElementById('otherDiscount').addEventListener('change', function () {
        const detailsTextarea = document.getElementById('otherDiscountDetails');
        if (this.checked) {
            // Muestra el cuadro de texto si el checkbox está marcado
            detailsTextarea.classList.remove('d-none');
        } else {
            // Oculta el cuadro de texto si el checkbox está desmarcado
            detailsTextarea.classList.add('d-none');
        }
    });
</script>

            <h3>Consent</h3>
            <div class="form-check mb-3">
                <input type="checkbox" id="consent" name="consent" class="form-check-input" required>
                <label class="form-check-label" for="consent">I confirm that I have read and reviewed the pre-enrollment form</label>
            </div>

            <button type="submit" class="btn btn-primary">Submit</button>
        </form>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const subjectsData = {
                1: [
                    { code: "07977", name: "Architectural Drawing", term: "Sem.1", credits: 9 },
                    { code: "07980", name: "History of Art and Architecture", term: "Sem.1", credits: 6 },
                    { code: "07975", name: "Mathematics", term: "Sem.1", credits: 6 },
                    { code: "07978", name: "Spatial and Formal Analysis", term: "Sem.1", credits: 9 },
                    { code: "07979", name: "Computational Design", term: "Sem.2", credits: 9 },
                    { code: "07982", name: "Design Studio 0", term: "Sem.2", credits: 6 },
                    { code: "07981", name: "Introduction to Architectural Construction", term: "Sem.2", credits: 6 },
                    { code: "07976", name: "Physics", term: "Sem.2", credits: 9 }
                ],
                2: [
                    { code: "07986", name: "Architectural Composition I", term: "Sem.1", credits: 6 },
                    { code: "07983", name: "Building Construction I", term: "Sem.1", credits: 5 },
                    { code: "07993", name: "Critical Thinking I", term: "Sem.1", credits: 5 },
                    { code: "07988", name: "Design Studio I", term: "Sem.1", credits: 5 },
                    { code: "07992", name: "English I", term: "Sem.1", credits: 5 },
                    { code: "07985", name: "Structural Calculation I", term: "Sem.1", credits: 5 },
                    { code: "07990", name: "Vertical Workshop I", term: "Sem.1", credits: 1 },
                    { code: "07987", name: "Architectural Composition II", term: "Sem.2", credits: 6 },
                    { code: "07984", name: "Building Construction II", term: "Sem.2", credits: 5 },
                    { code: "07994", name: "Critical Thinking II", term: "Sem.2", credits: 5 },
                    { code: "07989", name: "Design Studio II", term: "Sem.2", credits: 5 },
                    { code: "07995", name: "Foros I", term: "Sem.2", credits: 1 },
                    { code: "07991", name: "Urban Design I", term: "Sem.2", credits: 6 }
                ],
                3: [
                    { code: "08087", name: "Accessibility", term: "Sem.1", credits: 2.5 },
                    { code: "08000", name: "Architectural Composition III", term: "Sem.1", credits: 6 },
                    { code: "07996", name: "Building Construction III", term: "Sem.1", credits: 5.5 },
                    { code: "08088", name: "Design Studio III", term: "Sem.1", credits: 5 },
                    { code: "08092", name: "English II", term: "Sem.1", credits: 4.5 },
                    { code: "08091", name: "Urban Design II", term: "Sem.1", credits: 5.5 },
                    { code: "08090", name: "Vertical Workshop II", term: "Sem.1", credits: 1 },
                    { code: "08001", name: "Architectural Composition IV", term: "Sem.2", credits: 6 },
                    { code: "07997", name: "Building Construction IV", term: "Sem.2", credits: 5 },
                    { code: "07999", name: "Building Mechanics and Facilities I", term: "Sem.2", credits: 5 },
                    { code: "08089", name: "Design Studio IV", term: "Sem.2", credits: 5 },
                    { code: "08093", name: "Ethics", term: "Sem.2", credits: 3 },
                    { code: "08094", name: "Foros II", term: "Sem.2", credits: 1 },
                    { code: "07998", name: "Structural Calculation II", term: "Sem.2", credits: 5 }
                ],
                4: [
                    { code: "08102", name: "Architectural Theory and Criticism", term: "Sem.1", credits: 2.5 },
                    { code: "08095", name: "Building Construction V", term: "Sem.1", credits: 6.5 },
                    { code: "08098", name: "Building Mechanics and Facilities II", term: "Sem.1", credits: 5 },
                    { code: "08099", name: "Cooperation I", term: "Sem.1", credits: 3 },
                    { code: "08103", name: "Design Studio V", term: "Sem.1", credits: 5.5 },
                    { code: "08108", name: "Elective Course I", term: "Sem.1", credits: 3 },
                    { code: "08101", name: "Sustainability I", term: "Sem.1", credits: 2.5 },
                    { code: "08105", name: "Vertical Workshop III", term: "Sem.1", credits: 1 },
                    { code: "08096", name: "Building Construction VI", term: "Sem.2", credits: 6.5 },
                    { code: "08100", name: "Cooperation II", term: "Sem.2", credits: 3 },
                    { code: "08104", name: "Design Studio VI", term: "Sem.2", credits: 5.5 },
                    { code: "08109", name: "ESARQ Option 3", term: "Sem.2", credits: 3 },
                    { code: "08107", name: "Foros III", term: "Sem.2", credits: 1 },
                    { code: "08097", name: "Structural Calculation III", term: "Sem.2", credits: 6 },
                    { code: "08106", name: "Urban Design III", term: "Sem.2", credits: 6 },
                    { code: "08146", name: "Ceramics Chair (Elective)", term: "Sem.1", credits: 3 },
                    { code: "15313", name: "Introduction to BIM (Elective)", term: "Sem.1", credits: 3 },
                    { code: "12354", name: "Theory and Practice in the Restoration of Architectural Heritage (Elective)", term: "Sem.2", credits: 3 }
                ],
                5: [
                    { code: "08136", name: "Design Studio VII", term: "Sem.1", credits: 6.5 },
                    { code: "08134", name: "Management", term: "Sem.1", credits: 3 },
                    { code: "08132", name: "Professional Ethics", term: "Sem.1", credits: 3 },
                    { code: "08135", name: "Sustainability II", term: "Sem.1", credits: 3.5 },
                    { code: "08138", name: "Vertical Workshop IV", term: "Sem.1", credits: 1.5 },
                    { code: "08144", name: "Work Experience", term: "Sem.1", credits: 6 },
                    { code: "08133", name: "Building Construction VII", term: "Sem.2", credits: 5.5 },
                    { code: "08137", name: "Design Studio VIII", term: "Sem.2", credits: 7 },
                    { code: "08143", name: "Final Degree Project", term: "Sem.2", credits: 15 },
                    { code: "08140", name: "Foros IV", term: "Sem.2", credits: 1.5 },
                    { code: "08139", name: "Urban Design IV", term: "Sem.2", credits: 1.5 },
                    { code: "14041", name: "Designing Healthy Public Spaces (Elective)", term: "Sem.2", credits: 3 },
                    { code: "15312", name: "Metabolic Materiality (Elective)", term: "Sem.2", credits: 3 },
                    { code: "14066", name: "Construction of the Ephemeral Installation Llum BCN (Elective)", term: "Sem.1", credits: 3 }
                ]
            };

            const incompatibilities = {
                "07996": ["07984", "07983", "07981"],
                "08091": ["07991"],
                "08103": ["08089", "08088", "07989", "07988", "07982"]
            };

            const subjectsDiv = document.getElementById('subjects');
            let totalCredits = 0;

            function showAlert(message) {
                alert(message);
            }

            function updateCreditsDisplay() {
                document.getElementById('totalCredits').value = totalCredits;
            }

            for (const [course, subjects] of Object.entries(subjectsData)) {
                const courseTitle = document.createElement('h4');
                courseTitle.textContent = `Course ${course}`;
                subjectsDiv.appendChild(courseTitle);

                subjects.forEach(subject => {
                    const subjectRow = document.createElement('div');
                    subjectRow.classList.add('form-check');

                    const checkbox = document.createElement('input');
                    checkbox.type = 'checkbox';
                    checkbox.id = subject.code;
                    checkbox.name = 'subjects';
                    checkbox.value = subject.credits;
                    checkbox.dataset.name = subject.name;
                    checkbox.classList.add('form-check-input');

                    checkbox.addEventListener('change', () => {
                        if (checkbox.checked) {
                            totalCredits += parseFloat(subject.credits);

                            const conflicts = incompatibilities[subject.code] || [];
                            conflicts.forEach(conflictCode => {
                                const conflictingCheckbox = document.getElementById(conflictCode);
                                if (conflictingCheckbox && conflictingCheckbox.checked) {
                                    showAlert(`You cannot select ${subject.name} because it is incompatible with another selected subject.`);
                                    checkbox.checked = false;
                                    totalCredits -= parseFloat(subject.credits);
                                }
                            });
                        } else {
                            totalCredits -= parseFloat(subject.credits);
                        }
                        updateCreditsDisplay();
                    });

                    const label = document.createElement('label');
                    label.htmlFor = subject.code;
                    label.classList.add('form-check-label');
                    label.textContent = `${subject.code} - ${subject.name} (${subject.term}) - ${subject.credits} créditos`;

                    subjectRow.appendChild(checkbox);
                    subjectRow.appendChild(label);
                    subjectsDiv.appendChild(subjectRow);
                });

              }
        });
    </script>
</body>
</html>
