# CppExperience
Name | Description | Definition
------------ | ------------- | -------------
all_of | Test condition on all elements in range | bool all_of (InputIterator first, InputIterator last, UnaryPredicate pred);
any_of | Test if any element in range fulfills condition | bool any_of (InputIterator first, InputIterator last, UnaryPredicate pred);
none_of | Test if no elements fulfill condition | bool none_of (InputIterator first, InputIterator last, UnaryPredicate pred);
for_each |Apply function to range | Function for_each (InputIterator first, InputIterator last, Function fn)
find | Find value in range | InputIterator find (InputIterator first, InputIterator last, const T& val)
find_if | Find element in range | InputIterator find_if (InputIterator first, InputIterator last, UnaryPredicate pred)
find_if_not | Find element in range (negative condition) | InputIterator find_if_not (InputIterator first, InputIterator last, UnaryPredicate pred)
find_end | Find last subsequence in range | ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,
                              ForwardIterator2 first2, ForwardIterator2 last2);<br>ForwardIterator1 find_end (ForwardIterator1 first1, ForwardIterator1 last1,ForwardIterator2 first2, ForwardIterator2 last2, BinaryPredicate pred)
find_first_of | Find element from set in range | 
   ForwardIterator1 find_first_of (ForwardIterator1 first1, ForwardIterator1 last1,
                                   ForwardIterator2 first2, ForwardIterator2 last2);<br/>
   ForwardIterator1 find_first_of (ForwardIterator1 first1, ForwardIterator1 last1,
                                   ForwardIterator2 first2, ForwardIterator2 last2,
                                   BinaryPredicate pred);<br/>
   InputIterator find_first_of (InputIterator first1, InputIterator last1,
                                   ForwardIterator first2, ForwardIterator last2);<br/>
   InputIterator find_first_of (InputIterator first1, InputIterator last1,
                                   ForwardIterator first2, ForwardIterator last2,BinaryPredicate pred)
adjacent_find | Find equal adjacent elements in range | 
   ForwardIterator adjacent_find (ForwardIterator first, ForwardIterator last);
   ForwardIterator adjacent_find (ForwardIterator first, ForwardIterator last,BinaryPredicate pred)
count | Count appearances of value in range | typename iterator_traits<InputIterator>::difference_type
                                                   count (InputIterator first, InputIterator last, const T& val)
count_if | Return number of elements in range satisfying condition | typename iterator_traits<InputIterator>::difference_type
    count_if (InputIterator first, InputIterator last, UnaryPredicate pred)
mismatch | Return first position where two ranges differ | pair<InputIterator1, InputIterator2> mismatch (InputIterator1 first1, InputIterator1 last1,InputIterator2 first2);<br/>
  pair<InputIterator1, InputIterator2> mismatch (InputIterator1 first1, InputIterator1 last1,InputIterator2 first2,BinaryPredicate pred)
equal | Test whether the elements in two ranges are equal | bool equal (InputIterator1 first1, InputIterator1 last1, InputIterator2 first2);<br/>
 bool equal (InputIterator1 first1, InputIterator1 last1,
              InputIterator2 first2, BinaryPredicate pred)
is_permutation | Test whether range is permutation of another |
   bool is_permutation (ForwardIterator1 first1, ForwardIterator1 last1,
                        ForwardIterator2 first2);<br/>
   bool is_permutation (ForwardIterator1 first1, ForwardIterator1 last1,
                        ForwardIterator2 first2, BinaryPredicate pred)
search | Search range for subsequence |
   ForwardIterator1 search (ForwardIterator1 first1, ForwardIterator1 last1,
                            ForwardIterator2 first2, ForwardIterator2 last2);<br/>
   ForwardIterator1 search (ForwardIterator1 first1, ForwardIterator1 last1,
                            ForwardIterator2 first2, ForwardIterator2 last2,
                            BinaryPredicate pred)
search_n | Search range for elements |
   ForwardIterator search_n (ForwardIterator first, ForwardIterator last,
                             Size count, const T& val);<br/>
template <class ForwardIterator, class Size, class T, class BinaryPredicate>
   ForwardIterator search_n ( ForwardIterator first, ForwardIterator last,
                              Size count, const T& val, BinaryPredicate pred )
copy |Copy range of elements | template <class InputIterator, class OutputIterator>
  OutputIterator copy (InputIterator first, InputIterator last, OutputIterator result)
copy_n |Copy elements | template <class InputIterator, class Size, class OutputIterator>
  OutputIterator copy_n (InputIterator first, Size n, OutputIterator result)
copy_if |Copy certain elements of range | template <class InputIterator, class OutputIterator, class UnaryPredicate>
  OutputIterator copy_if (InputIterator first, InputIterator last,
                          OutputIterator result, UnaryPredicate pred)
copy_backward |Copy range of elements backward | template <class BidirectionalIterator1, class BidirectionalIterator2>
  BidirectionalIterator2 copy_backward (BidirectionalIterator1 first,
                                        BidirectionalIterator1 last,
                                        BidirectionalIterator2 result)
move |Move range of elements | template <class InputIterator, class OutputIterator>
  OutputIterator move (InputIterator first, InputIterator last, OutputIterator result)
move_backward |Move range of elements backward | template <class BidirectionalIterator1, class BidirectionalIterator2>
  BidirectionalIterator2 move_backward (BidirectionalIterator1 first,
                                        BidirectionalIterator1 last,
                                        BidirectionalIterator2 result)
swap |Exchange values of two objects | template <class T> void swap (T& a, T& b);

header
// moved from <algorithm> to <utility> in C++11
non-array (1)
template <class T> void swap (T& a, T& b)
  noexcept (is_nothrow_move_constructible<T>::value && is_nothrow_move_assignable<T>::value);
array (2)
template <class T, size_t N> void swap(T (&a)[N], T (&b)[N])
  noexcept (noexcept(swap(*a,*b)))
swap_ranges |Exchange values of two ranges | template <class ForwardIterator1, class ForwardIterator2>
  ForwardIterator2 swap_ranges (ForwardIterator1 first1, ForwardIterator1 last1,
                                ForwardIterator2 first2)
iter_swap |Exchange values of objects pointed to by two iterators | template <class ForwardIterator1, class ForwardIterator2>
  void iter_swap (ForwardIterator1 a, ForwardIterator2 b)
transform |Transform range | unary operation(1)
template <class InputIterator, class OutputIterator, class UnaryOperation>
  OutputIterator transform (InputIterator first1, InputIterator last1,
                            OutputIterator result, UnaryOperation op);
binary operation(2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class BinaryOperation>
  OutputIterator transform (InputIterator1 first1, InputIterator1 last1,
                            InputIterator2 first2, OutputIterator result,
                            BinaryOperation binary_op)
replace |Replace value in range | template <class ForwardIterator, class T>
  void replace (ForwardIterator first, ForwardIterator last,
                const T& old_value, const T& new_value)
replace_if |Replace values in range | template <class ForwardIterator, class UnaryPredicate, class T>
  void replace_if (ForwardIterator first, ForwardIterator last,
                   UnaryPredicate pred, const T& new_value )
replace_copy |Copy range replacing value | template <class InputIterator, class OutputIterator, class T>
  OutputIterator replace_copy (InputIterator first, InputIterator last,
                               OutputIterator result,
                               const T& old_value, const T& new_value)
replace_copy_if |Copy range replacing value | template <class InputIterator, class OutputIterator, class UnaryPredicate, class T>
  OutputIterator replace_copy_if (InputIterator first, InputIterator last,
                                  OutputIterator result, UnaryPredicate pred,
                                  const T& new_value)
fill |Fill range with value | template <class ForwardIterator, class T>
  void fill (ForwardIterator first, ForwardIterator last, const T& val)
fill_n |Fill sequence with value | template <class OutputIterator, class Size, class T>
  void fill_n (OutputIterator first, Size n, const T& val);

template <class OutputIterator, class Size, class T>
  OutputIterator fill_n (OutputIterator first, Size n, const T& val)
generate |Generate values for range with function | template <class ForwardIterator, class Generator>
  void generate (ForwardIterator first, ForwardIterator last, Generator gen)
generate_n |Generate values for sequence with function | template <class OutputIterator, class Size, class Generator>
  void generate_n (OutputIterator first, Size n, Generator gen);

template <class OutputIterator, class Size, class Generator>
  OutputIterator generate_n (OutputIterator first, Size n, Generator gen)
remove |Remove value from range | template <class ForwardIterator, class T>
  ForwardIterator remove (ForwardIterator first, ForwardIterator last, const T& val)
remove_if |Remove elements from range | template <class ForwardIterator, class UnaryPredicate>
  ForwardIterator remove_if (ForwardIterator first, ForwardIterator last,
                             UnaryPredicate pred)
remove_copy |Copy range removing value | template <class InputIterator, class OutputIterator, class T>
  OutputIterator remove_copy (InputIterator first, InputIterator last,
                              OutputIterator result, const T& val)
remove_copy_if |Copy range removing values | template <class InputIterator, class OutputIterator, class UnaryPredicate>
  OutputIterator remove_copy_if (InputIterator first, InputIterator last,
                                 OutputIterator result, UnaryPredicate pred)
unique |Remove consecutive duplicates in range | equality (1)
template <class ForwardIterator>
  ForwardIterator unique (ForwardIterator first, ForwardIterator last);
predicate (2)
template <class ForwardIterator, class BinaryPredicate>
  ForwardIterator unique (ForwardIterator first, ForwardIterator last,
                          BinaryPredicate pred)
unique_copy |Copy range removing duplicates | equality (1)
template <class InputIterator, class OutputIterator>
  OutputIterator unique_copy (InputIterator first, InputIterator last,
                              OutputIterator result);
predicate (2)
template <class InputIterator, class OutputIterator, class BinaryPredicate>
  OutputIterator unique_copy (InputIterator first, InputIterator last,
                              OutputIterator result, BinaryPredicate pred)
reverse |Reverse range | template <class BidirectionalIterator>
  void reverse (BidirectionalIterator first, BidirectionalIterator last)
reverse_copy |Copy range reversed | template <class BidirectionalIterator, class OutputIterator>
  OutputIterator reverse_copy (BidirectionalIterator first,
                               BidirectionalIterator last, OutputIterator result)
rotate |Rotate left the elements in range | template <class ForwardIterator>
  void rotate (ForwardIterator first, ForwardIterator middle,
               ForwardIterator last);

template <class ForwardIterator>
  ForwardIterator rotate (ForwardIterator first, ForwardIterator middle,
                          ForwardIterator last)
rotate_copy |Copy range rotated left | template <class ForwardIterator, class OutputIterator>
  OutputIterator rotate_copy (ForwardIterator first, ForwardIterator middle,
                              ForwardIterator last, OutputIterator result)
random_shuffle |Randomly rearrange elements in range | generator by default (1)
template <class RandomAccessIterator>
  void random_shuffle (RandomAccessIterator first, RandomAccessIterator last);
specific generator (2)
template <class RandomAccessIterator, class RandomNumberGenerator>
  void random_shuffle (RandomAccessIterator first, RandomAccessIterator last,
                       RandomNumberGenerator& gen);

generator by default (1)
template <class RandomAccessIterator>
  void random_shuffle (RandomAccessIterator first, RandomAccessIterator last);
specific generator (2)
template <class RandomAccessIterator, class RandomNumberGenerator>
  void random_shuffle (RandomAccessIterator first, RandomAccessIterator last,
                       RandomNumberGenerator&& gen)
shuffle |Randomly rearrange elements in range using generator | template <class RandomAccessIterator, class URNG>
  void shuffle (RandomAccessIterator first, RandomAccessIterator last, URNG&& g)
is_partitioned |Test whether range is partitioned | template <class InputIterator, class UnaryPredicate>
  bool is_partitioned (InputIterator first, InputIterator last, UnaryPredicate pred)
partition |Partition range in two | template <class BidirectionalIterator, class UnaryPredicate>
  BidirectionalIterator partition (BidirectionalIterator first,
                                   BidirectionalIterator last, UnaryPredicate pred);

template <class ForwardIterator, class UnaryPredicate>
  ForwardIterator partition (ForwardIterator first,
                             ForwardIterator last, UnaryPredicate pred)
stable_partition |Partition range in two - stable ordering | template <class BidirectionalIterator, class UnaryPredicate>
  BidirectionalIterator stable_partition (BidirectionalIterator first,
                                          BidirectionalIterator last,
                                          UnaryPredicate pred)
partition_copy |Partition range into two | template <class InputIterator, class OutputIterator1,
          class OutputIterator2, class UnaryPredicate pred>
  pair<OutputIterator1,OutputIterator2>
    partition_copy (InputIterator first, InputIterator last,
                    OutputIterator1 result_true, OutputIterator2 result_false,
                    UnaryPredicate pred)
partition_point |Get partition point | template <class ForwardIterator, class UnaryPredicate>
  ForwardIterator partition_point (ForwardIterator first, ForwardIterator last,
                                   UnaryPredicate pred)
sort |Sort elements in range | default (1)
template <class RandomAccessIterator>
  void sort (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void sort (RandomAccessIterator first, RandomAccessIterator last, Compare comp)
stable_sort |Sort elements preserving order of equivalents | template <class RandomAccessIterator>
  void stable_sort ( RandomAccessIterator first, RandomAccessIterator last );

template <class RandomAccessIterator, class Compare>
  void stable_sort ( RandomAccessIterator first, RandomAccessIterator last,
                     Compare comp )
partial_sort |Partially sort elements in range | default (1)
template <class RandomAccessIterator>
  void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                     RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void partial_sort (RandomAccessIterator first, RandomAccessIterator middle,
                     RandomAccessIterator last, Compare comp)
partial_sort_copy |Copy and partially sort range | default (1)
template <class InputIterator, class RandomAccessIterator>
  RandomAccessIterator
    partial_sort_copy (InputIterator first,InputIterator last,
                       RandomAccessIterator result_first,
                       RandomAccessIterator result_last);
custom (2)
template <class InputIterator, class RandomAccessIterator, class Compare>
  RandomAccessIterator
    partial_sort_copy (InputIterator first,InputIterator last,
                       RandomAccessIterator result_first,
                       RandomAccessIterator result_last, Compare comp)
is_sorted |Check whether range is sorted | default (1)
template <class ForwardIterator>
  bool is_sorted (ForwardIterator first, ForwardIterator last);
custom (2)
template <class ForwardIterator, class Compare>
  bool is_sorted (ForwardIterator first, ForwardIterator last, Compare comp)
is_sorted_until |Find first unsorted element in range | default (1)
template <class ForwardIterator>
  ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last);
custom (2)
template <class ForwardIterator, class Compare>
  ForwardIterator is_sorted_until (ForwardIterator first, ForwardIterator last,
                                   Compare comp)
nth_element |Sort element in range | default (1)
template <class RandomAccessIterator>
  void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                    RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void nth_element (RandomAccessIterator first, RandomAccessIterator nth,
                    RandomAccessIterator last, Compare comp)
lower_bound |Return iterator to lower bound | default (1)
template <class ForwardIterator, class T>
  ForwardIterator lower_bound (ForwardIterator first, ForwardIterator last,
                               const T& val);
custom (2)
template <class ForwardIterator, class T, class Compare>
  ForwardIterator lower_bound (ForwardIterator first, ForwardIterator last,
                               const T& val, Compare comp)
upper_bound |Return iterator to upper bound | default (1)
template <class ForwardIterator, class T>
  ForwardIterator upper_bound (ForwardIterator first, ForwardIterator last,
                               const T& val);
custom (2)
template <class ForwardIterator, class T, class Compare>
  ForwardIterator upper_bound (ForwardIterator first, ForwardIterator last,
                               const T& val, Compare comp)
equal_range |Get subrange of equal elements | default (1)
template <class ForwardIterator, class T>
  pair<ForwardIterator,ForwardIterator>
    equal_range (ForwardIterator first, ForwardIterator last, const T& val);
custom (2)
template <class ForwardIterator, class T, class Compare>
  pair<ForwardIterator,ForwardIterator>
    equal_range (ForwardIterator first, ForwardIterator last, const T& val,
                  Compare comp)
binary_search |Test if value exists in sorted sequence | default (1)
template <class ForwardIterator, class T>
  bool binary_search (ForwardIterator first, ForwardIterator last,
                      const T& val);
custom (2)
template <class ForwardIterator, class T, class Compare>
  bool binary_search (ForwardIterator first, ForwardIterator last,
                      const T& val, Compare comp)
merge |Merge sorted ranges | default (1)
template <class InputIterator1, class InputIterator2, class OutputIterator>
  OutputIterator merge (InputIterator1 first1, InputIterator1 last1,
                        InputIterator2 first2, InputIterator2 last2,
                        OutputIterator result);
custom (2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class Compare>
  OutputIterator merge (InputIterator1 first1, InputIterator1 last1,
                        InputIterator2 first2, InputIterator2 last2,
                        OutputIterator result, Compare comp)
inplace_merge |Merge consecutive sorted ranges | default (1)
template <class BidirectionalIterator>
  void inplace_merge (BidirectionalIterator first, BidirectionalIterator middle,
                      BidirectionalIterator last);
custom (2)
template <class BidirectionalIterator, class Compare>
  void inplace_merge (BidirectionalIterator first, BidirectionalIterator middle,
                      BidirectionalIterator last, Compare comp)
includes |Test whether sorted range includes another sorted range | template <class InputIterator1, class InputIterator2>
  bool includes ( InputIterator1 first1, InputIterator1 last1,
                  InputIterator2 first2, InputIterator2 last2 );

template <class InputIterator1, class InputIterator2, class Compare>
  bool includes ( InputIterator1 first1, InputIterator1 last1,
                  InputIterator2 first2, InputIterator2 last2, Compare comp )
set_union |Union of two sorted ranges | default (1)
template <class InputIterator1, class InputIterator2, class OutputIterator>
  OutputIterator set_union (InputIterator1 first1, InputIterator1 last1,
                            InputIterator2 first2, InputIterator2 last2,
                            OutputIterator result);
custom (2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class Compare>
  OutputIterator set_union (InputIterator1 first1, InputIterator1 last1,
                            InputIterator2 first2, InputIterator2 last2,
                            OutputIterator result, Compare comp)
set_intersection |Intersection of two sorted ranges | default (1)
template <class InputIterator1, class InputIterator2, class OutputIterator>
  OutputIterator set_intersection (InputIterator1 first1, InputIterator1 last1,
                                   InputIterator2 first2, InputIterator2 last2,
                                   OutputIterator result);
custom (2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class Compare>
  OutputIterator set_intersection (InputIterator1 first1, InputIterator1 last1,
                                   InputIterator2 first2, InputIterator2 last2,
                                   OutputIterator result, Compare comp)
set_difference |Difference of two sorted ranges | default (1)
template <class InputIterator1, class InputIterator2, class OutputIterator>
  OutputIterator set_difference (InputIterator1 first1, InputIterator1 last1,
                                 InputIterator2 first2, InputIterator2 last2,
                                 OutputIterator result);
custom (2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class Compare>
  OutputIterator set_difference (InputIterator1 first1, InputIterator1 last1,
                                 InputIterator2 first2, InputIterator2 last2,
                                 OutputIterator result, Compare comp)
set_symmetric_difference |Symmetric difference of two sorted ranges | default (1)
template <class InputIterator1, class InputIterator2, class OutputIterator>
  OutputIterator set_symmetric_difference (InputIterator1 first1, InputIterator1 last1,
                                           InputIterator2 first2, InputIterator2 last2,
                                           OutputIterator result);
custom (2)
template <class InputIterator1, class InputIterator2,
          class OutputIterator, class Compare>
  OutputIterator set_symmetric_difference (InputIterator1 first1, InputIterator1 last1,
                                           InputIterator2 first2, InputIterator2 last2,
                                           OutputIterator result, Compare comp)
push_heap |Push element into heap range | default (1)
template <class RandomAccessIterator>
  void push_heap (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void push_heap (RandomAccessIterator first, RandomAccessIterator last,
                   Compare comp)
pop_heap |Pop element from heap range | default (1)
template <class RandomAccessIterator>
  void pop_heap (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void pop_heap (RandomAccessIterator first, RandomAccessIterator last,
                 Compare comp)
make_heap |Make heap from range | default (1)
template <class RandomAccessIterator>
  void make_heap (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void make_heap (RandomAccessIterator first, RandomAccessIterator last,
                  Compare comp )
sort_heap |Sort elements of heap | default (1)
template <class RandomAccessIterator>
  void sort_heap (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  void sort_heap (RandomAccessIterator first, RandomAccessIterator last,
                  Compare comp)
is_heap |Test if range is heap | default (1)
template <class RandomAccessIterator>
  bool is_heap (RandomAccessIterator first, RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  bool is_heap (RandomAccessIterator first, RandomAccessIterator last,
                Compare comp)
is_heap_until |Find first element not in heap order | default (1)
template <class RandomAccessIterator>
  RandomAccessIterator is_heap_until (RandomAccessIterator first,
                                      RandomAccessIterator last);
custom (2)
template <class RandomAccessIterator, class Compare>
  RandomAccessIterator is_heap_until (RandomAccessIterator first,
                                      RandomAccessIterator last
                                      Compare comp)
min |Return the smallest | default (1)
template <class T> const T& min (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  const T& min (const T& a, const T& b, Compare comp);

default (1)
template <class T> const T& min (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  const T& min (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T> T min (initializer_list<T> il);
template <class T, class Compare>
  T min (initializer_list<T> il, Compare comp);

default (1)
template <class T> constexpr const T& min (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  constexpr const T& min (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T> constexpr T min (initializer_list<T> il);
template <class T, class Compare>
  constexpr T min (initializer_list<T> il, Compare comp)
max |Return the largest | default (1)
template <class T> const T& max (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  const T& max (const T& a, const T& b, Compare comp);

default (1)
template <class T> const T& max (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  const T& max (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T> T max (initializer_list<T> il);
template <class T, class Compare>
  T max (initializer_list<T> il, Compare comp);

default (1)
template <class T> constexpr const T& max (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  constexpr const T& max (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T> constexpr T max (initializer_list<T> il);
template <class T, class Compare>
  constexpr T max (initializer_list<T> il, Compare comp)
minmax |Return smallest and largest elements | default (1)
template <class T>
  pair <const T&,const T&> minmax (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  pair <const T&,const T&> minmax (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T>
  pair<T,T> minmax (initializer_list<T> il);
template <class T, class Compare>
  pair<T,T> minmax (initializer_list<T> il, Compare comp);

default (1)
template <class T>
  constexpr pair <const T&,const T&> minmax (const T& a, const T& b);
custom (2)
template <class T, class Compare>
  constexpr pair <const T&,const T&> minmax (const T& a, const T& b, Compare comp);
initializer list (3)
template <class T>
  constexpr pair<T,T> minmax (initializer_list<T> il);
template <class T, class Compare>
  constexpr pair<T,T> minmax (initializer_list<T> il, Compare comp)
min_element |Return smallest element in range | default (1)
template <class ForwardIterator>
  ForwardIterator min_element (ForwardIterator first, ForwardIterator last);
custom (2)
template <class ForwardIterator, class Compare>
  ForwardIterator min_element (ForwardIterator first, ForwardIterator last,
                               Compare comp)
max_element |Return largest element in range | default (1)
template <class ForwardIterator>
  ForwardIterator max_element (ForwardIterator first, ForwardIterator last);
custom (2)
template <class ForwardIterator, class Compare>
  ForwardIterator max_element (ForwardIterator first, ForwardIterator last,
                               Compare comp)
minmax_element |Return smallest and largest elements in range | default (1)
template <class ForwardIterator>
  pair<ForwardIterator,ForwardIterator>
    minmax_element (ForwardIterator first, ForwardIterator last);
custom (2)
template <class ForwardIterator, class Compare>
  pair<ForwardIterator,ForwardIterator>
    minmax_element (ForwardIterator first, ForwardIterator last, Compare comp)
lexicographical_compare |Lexicographical less-than comparison | default (1)
template <class InputIterator1, class InputIterator2>
  bool lexicographical_compare (InputIterator1 first1, InputIterator1 last1,
                                InputIterator2 first2, InputIterator2 last2);
custom (2)
template <class InputIterator1, class InputIterator2, class Compare>
  bool lexicographical_compare (InputIterator1 first1, InputIterator1 last1,
                                InputIterator2 first2, InputIterator2 last2,
                                Compare comp)
next_permutation |Transform range to next permutation | default (1)
template <class BidirectionalIterator>
  bool next_permutation (BidirectionalIterator first,
                         BidirectionalIterator last);
custom (2)
template <class BidirectionalIterator, class Compare>
  bool next_permutation (BidirectionalIterator first,
                         BidirectionalIterator last, Compare comp)
prev_permutation |Transform range to previous permutation | default (1)
template <class BidirectionalIterator>
  bool prev_permutation (BidirectionalIterator first,
                         BidirectionalIterator last );
custom (2)
template <class BidirectionalIterator, class Compare>
  bool prev_permutation (BidirectionalIterator first,
                         BidirectionalIterator last, Compare comp)

