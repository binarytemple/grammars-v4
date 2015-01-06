all: compile

compile:
	antlr4 Erlang.g4
	javac -cp /usr/local/Cellar/antlr/4.4/antlr-4.4-complete.jar Erlang*.java

debug: compile
	java -cp /usr/local/Cellar/antlr/4.4/antlr-4.4-complete.jar org.antlr.v4.runtime.misc.TestRig  Erlang forms -gui -encoding utf8 ./app.config

gui: compile
	java -cp /usr/local/Cellar/antlr/4.4/antlr-4.4-complete.jar:. org.antlr.v4.runtime.misc.TestRig Erlang form -tokens -tree -gui ./app.config

check: compile
	./check.sh test/

clean:
	rm -f *.class

distclean: clean
	rm -f *.java *.tokens
