CMAKE_MINIMUM_REQUIRED(VERSION 2.4)
SET(CMAKE_C_FLAGS_RELEASE "-Wall -O2")
SET(CMAKE_C_FLAGS_DEBUG "-g")
SET(CMAKE_BUILD_TYPE Release)

# プロジェクト名
PROJECT(read2ch C)
INCLUDE_DIRECTORIES(
	"${PROJECT_SOURCE_DIR}"
	/usr/local/include/
	/opt/local/include/
	/usr/local/mysql/include/
	/opt/local/mysql/include/
)
LINK_DIRECTORIES(
	/usr/local/lib/
	/opt/local/lib/
	/usr/local/mysql/lib/
)
# 実行ファイル
ADD_EXECUTABLE(read2ch read.c)
TARGET_LINK_LIBRARIES(read2ch un2ch pthread mysqlclient onig unmap unstring unarray)

