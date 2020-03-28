#---------------------------
func1 := ${subst not, totally, "I am not superman"}

#---------------------------
comma := ,
empty:=
space := $(empty) $(empty)
foo2 := a b c
func2 := $(subst $(space),$(comma),$(foo2))

#---------------------------
# For each "word" in foo, output that same word with an exclamation after
foo3 := who are you
func3 := $(foreach wrd,$(foo3),$(wrd)!)

#---------------------------
foo4 := $(if this-is-not-empty,then!,else!)
empty :=
func4 := $(if $(empty),then!,else!)

#---------------------------
sweet_new_fn = Variable Name: $(0) First: $(1) Second: $(2) Empty Variable: $(3)




all: f1 f2 f3 f4 f5 f6 

f1:
	@echo "function 1 ----" 
	@echo $(func1)

f2:
	@echo "function 2 ----" 
	@echo $(func2)

f3:
	@echo "function 3 ----" 
	@echo $(func3)

f4:
	@echo "function 4 ----" 
	@echo $(foo4)
	@echo $(func4)

f5:
# Outputs "Variable Name: sweet_new_fn First: go Second: tigers Empty Variable:"
	@echo "function 5 ----" 
	@echo $(call sweet_new_fn, go, tigers)

f6:
	@echo "function 6 ----" 
	@echo $(shell ls -la) # Very ugly because the newlines are gone!

clean:
	@echo "There is no file to clean!"
