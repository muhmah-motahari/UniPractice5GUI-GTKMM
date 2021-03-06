cmake_minimum_required(VERSION 3.0)

project(ExamWare)

# C++11 standards
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED true)

add_executable(${PROJECT_NAME}
    src/main.cpp

    # Questions
    src/Question/Question.cpp
    src/Question/FourChoicesQuestion.cpp
    src/Question/BlankFillingQuestion.cpp
    src/Question/TextualQuestion.cpp

    # Answers
    src/Answer/BlankFillingAnswer.cpp
    src/Answer/FourChoicesAnswer.cpp
    src/Answer/TextualAnswer.cpp

    # Exam-related
    src/Exam/Exam.cpp
    src/Exam/ExamAccess.cpp
    src/Exam/ExamMasterAccess.cpp
    src/Exam/ExamStudentAccess.cpp

    # Users
    src/User/User.cpp
    src/User/Master.cpp
    src/User/Student.cpp
    src/User/UserSerializer.cpp

    src/Course.cpp
    src/AnswerSheet.cpp
    src/LoginManager.cpp
    src/UserDataManager.cpp
    src/Util.cpp

		# GUI
		src/GUI/MainWindow.cpp
		src/GUI/LoginPage.cpp
		src/GUI/Handler.cpp
		src/GUI/AddExamPage.cpp
		src/GUI/FirstPage_master.cpp
		src/GUI/RegisterStudentPage.cpp
)

target_include_directories(${PROJECT_NAME} PUBLIC
	include/

  # GUI	
	/usr/include/gtkmm-3.0 
	/usr/lib/x86_64-linux-gnu/gtkmm-3.0/include 
	/usr/include/atkmm-1.6 
	/usr/include/gtk-3.0/unix-print 
	/usr/include/gdkmm-3.0 
	/usr/lib/x86_64-linux-gnu/gdkmm-3.0/include 
	/usr/include/giomm-2.4 
	/usr/lib/x86_64-linux-gnu/giomm-2.4/include 
	/usr/include/pangomm-1.4 
	/usr/lib/x86_64-linux-gnu/pangomm-1.4/include 
	/usr/include/glibmm-2.4 
	/usr/lib/x86_64-linux-gnu/glibmm-2.4/include 
	/usr/include/gtk-3.0 
	/usr/include/at-spi2-atk/2.0 
	/usr/include/at-spi-2.0 
	/usr/include/dbus-1.0 
	/usr/lib/x86_64-linux-gnu/dbus-1.0/include 
	/usr/include/gtk-3.0 
	/usr/include/gio-unix-2.0 
	/usr/include/cairo 
	/usr/include/pango-1.0 
	/usr/include/fribidi 
	/usr/include/harfbuzz 
	/usr/include/atk-1.0 
	/usr/include/cairo 
	/usr/include/cairomm-1.0 
	/usr/lib/x86_64-linux-gnu/cairomm-1.0/include 
	/usr/include/cairo 
	/usr/include/pixman-1 
	/usr/include/uuid 
	/usr/include/freetype2 
	/usr/include/libpng16 
	/usr/include/sigc++-2.0 
	/usr/lib/x86_64-linux-gnu/sigc++-2.0/include 
	/usr/include/gdk-pixbuf-2.0 
	/usr/include/libmount 
	/usr/include/blkid 
	/usr/include/glib-2.0 
	/usr/lib/x86_64-linux-gnu/glib-2.0/include
)

target_link_libraries(${PROJECT_NAME}
	-lgtkmm-3.0 
	-latkmm-1.6 
	-lgdkmm-3.0 
	-lgiomm-2.4 
	-lpangomm-1.4 
	-lglibmm-2.4 
	-lgtk-3 
	-lgdk-3 
	-lpangocairo-1.0 
	-lpango-1.0 
	-lharfbuzz 
	-latk-1.0 
	-lcairo-gobject 
	-lgio-2.0 
	-lcairomm-1.0 
	-lcairo 
	-lsigc-2.0 
	-lgdk_pixbuf-2.0 
	-lgobject-2.0 
	-lglib-2.0
)
