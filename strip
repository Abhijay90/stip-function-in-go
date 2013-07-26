//Simple strip function from python for go.
//syntax for input strip(original string,pattern to strip)
package strip

import "fmt"

func stringcheck(s string, pat string, ls int, lp int) int {
  c := []byte(s)
	d := []byte(pat)
	count := 0
	beg := 0
	for i := 0; i < ls; i++ {
		if c[i] != d[count] {
			break
		}
		if (i+1)%lp == 0 {
			beg = i + 1
		}
		if i == ls-1 {
			beg = i
		}
		count++
		if count == lp {
			count = 0
		}
	}
	return beg
}

func stringreverse(s string, ls int) string {
	c := []byte(s)
	d := make([]byte, ls)
	for i := 0; i < ls; i++ {
		d[i] = c[ls-i-1]
	}
	s = string(d)
	return s
}

func strip(s string, pat string) string {
	ls := len(s)
	lp := len(pat)
	c := []byte(s)
	if lp == 0 {
		pat = " "
		lp = 1
	}
	beg := 0
	end := ls - 1
	beg = stringcheck(s, pat, ls, lp)
	if beg != end {
		s = stringreverse(s, ls)
		pat = stringreverse(pat, lp)
		end = stringcheck(s, pat, ls, lp)
		end = ls - end
	}
	sr := ""
	count := 0
	str := make([]byte, end-beg+1)
	for i := beg; i < end; i++ {
		str[count] = c[i]
		count++
	}
	sr = string(str)
	return sr
}
