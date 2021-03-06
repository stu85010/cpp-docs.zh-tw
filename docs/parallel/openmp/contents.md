---
title: 內容
ms.date: 11/04/2016
ms.assetid: b7858099-7d7f-4cd9-9fa0-fba4832f2dd2
ms.openlocfilehash: f9fffab938735421429c53cc760ad0db16484577
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620580"
---
# <a name="contents"></a>內容

[1.簡介](../../parallel/openmp/1-introduction.md)

[1.1 範圍](../../parallel/openmp/1-1-scope.md)

[1.2 詞彙定義](../../parallel/openmp/1-2-definition-of-terms.md)

[1.3 執行模式](../../parallel/openmp/1-3-execution-model.md)

[1.4 符合標準](../../parallel/openmp/1-4-compliance.md)

[1.5 規範參考](../../parallel/openmp/1-5-normative-references.md)

[1.6 組織](../../parallel/openmp/1-6-organization.md)

[2.指示詞](../../parallel/openmp/2-directives.md)

[2.1 指示詞格式](../../parallel/openmp/2-1-directive-format.md)

[2.2 條件式編譯](../../parallel/openmp/2-2-conditional-compilation.md)

[2.3 parallel 建構](../../parallel/openmp/2-3-parallel-construct.md)

[2.4 工作共用的建構](../../parallel/openmp/2-4-work-sharing-constructs.md)

[2.4.1 for 建構](../../parallel/openmp/2-4-1-for-construct.md)

[2.4.2 sections 建構](../../parallel/openmp/2-4-2-sections-construct.md)

[2.4.3 single 建構](../../parallel/openmp/2-4-3-single-construct.md)

[2.5 合併的平行工作共用建構](../../parallel/openmp/2-5-combined-parallel-work-sharing-constructs.md)

[2.5.1 parallel for 建構](../../parallel/openmp/2-5-1-parallel-for-construct.md)

[2.5.2 parallel sections 建構](../../parallel/openmp/2-5-2-parallel-sections-construct.md)

[2.6 主執行緒和同步處理指示詞](../../parallel/openmp/2-6-master-and-synchronization-directives.md)

[2.6.1 master 建構](../../parallel/openmp/2-6-1-master-construct.md)

[2.6.2 critical 建構](../../parallel/openmp/2-6-2-critical-construct.md)

[2.6.3 barrier 指示詞](../../parallel/openmp/2-6-3-barrier-directive.md)

[2.6.4 atomic 建構](../../parallel/openmp/2-6-4-atomic-construct.md)

[2.6.5 flush 指示詞](../../parallel/openmp/2-6-5-flush-directive.md)

[2.6.6 ordered 建構](../../parallel/openmp/2-6-6-ordered-construct.md)

[2.7 資料環境](../../parallel/openmp/2-7-data-environment.md)

[2.7.1 threadprivate 指示詞](../../parallel/openmp/2-7-1-threadprivate-directive.md)

[2.7.2 資料共用屬性子句](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md)

[2.7.2.1 private](../../parallel/openmp/2-7-2-1-private.md)

[2.7.2.2 firstprivate](../../parallel/openmp/2-7-2-2-firstprivate.md)

[2.7.2.3 lastprivate](../../parallel/openmp/2-7-2-3-lastprivate.md)

[2.7.2.4 shared](../../parallel/openmp/2-7-2-4-shared.md)

[2.7.2.5 default](../../parallel/openmp/2-7-2-5-default.md)

[2.7.2.6 reduction](../../parallel/openmp/2-7-2-6-reduction.md)

[2.7.2.7 copyin](../../parallel/openmp/2-7-2-7-copyin.md)

[2.7.2.8 copyprivate](../../parallel/openmp/2-7-2-8-copyprivate.md)

[2.8 指示詞繫結](../../parallel/openmp/2-8-directive-binding.md)

[2.9 巢狀使用指示詞](../../parallel/openmp/2-9-directive-nesting.md)

[3.執行階段程式庫函式](../../parallel/openmp/3-run-time-library-functions.md)

[3.1 執行環境函式](../../parallel/openmp/3-1-execution-environment-functions.md)

[3.1.1 omp_set_num_threads 函式](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)

[3.1.2 omp_get_num_threads 函式](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)

[3.1.3 omp_get_max_threads 函式](../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)

[3.1.4 omp_get_thread_num 函式](../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)

[3.1.5 omp_get_num_procs 函式](../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)

[3.1.6 omp_in_parallel 函式](../../parallel/openmp/3-1-6-omp-in-parallel-function.md)

[3.1.7 omp_set_dynamic 函式](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)

[3.1.8 omp_get_dynamic 函式](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md)

[3.1.9 omp_set_nested 函式](../../parallel/openmp/3-1-9-omp-set-nested-function.md)

[3.1.10 omp_get_nested 函式](../../parallel/openmp/3-1-10-omp-get-nested-function.md)

[3.2 鎖定函式](../../parallel/openmp/3-2-lock-functions.md)

[3.2.1 omp_init_lock 和 omp_init_nest_lock 函式](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)

[3.2.2 omp_destroy_lock 和 omp_destroy_nest_lock 函式](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)

[3.2.3 omp_set_lock 和 omp_set_nest_lock 函式](../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)

[3.2.4 omp_unset_lock 和 omp_unset_nest_lock 函式](../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)

[3.2.5 omp_test_lock 和 omp_test_nest_lock 函式](../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)

[3.3 計時常式](../../parallel/openmp/3-3-timing-routines.md)

[3.3.1 omp_get_wtime 函式](../../parallel/openmp/3-3-1-omp-get-wtime-function.md)

[3.3.2 omp_get_wtick 函式](../../parallel/openmp/3-3-2-omp-get-wtick-function.md)

[4.環境變數](../../parallel/openmp/4-environment-variables.md)

[4.1 OMP_SCHEDULE](../../parallel/openmp/4-1-omp-schedule.md)

[4.2 OMP_NUM_THREADS](../../parallel/openmp/4-2-omp-num-threads.md)

[4.3 OMP_DYNAMIC](../../parallel/openmp/4-3-omp-dynamic.md)

[4.4 OMP_NESTED](../../parallel/openmp/4-4-omp-nested.md)

[A.範例](../../parallel/openmp/a-examples.md)

[A.1 平行執行簡單迴圈](../../parallel/openmp/a-1-executing-a-simple-loop-in-parallel.md)

[A.2 指定條件式編譯](../../parallel/openmp/a-2-specifying-conditional-compilation.md)

[A.3 使用平行區域](../../parallel/openmp/a-3-using-parallel-regions.md)

[A.4 使用 nowait 子句](../../parallel/openmp/a-4-using-the-nowait-clause.md)

[A.5 使用 critical 指示詞](../../parallel/openmp/a-5-using-the-critical-directive.md)

[A.6 使用 lastprivate 子句](../../parallel/openmp/a-6-using-the-lastprivate-clause.md)

[A.7 使用 reduction 子句](../../parallel/openmp/a-7-using-the-reduction-clause.md)

[A.8 指定平行處理區段](../../parallel/openmp/a-8-specifying-parallel-sections.md)

[A.9 使用 single 指示詞](../../parallel/openmp/a-9-using-single-directives.md)

[A.10 指定循序排序](../../parallel/openmp/a-10-specifying-sequential-ordering.md)

[A.11 指定固定的執行緒數目](../../parallel/openmp/a-11-specifying-a-fixed-number-of-threads.md)

[A.12 使用 atomic 指示詞](../../parallel/openmp/a-12-using-the-atomic-directive.md)

[A.13 使用 flush 指示詞的清單並](../../parallel/openmp/a-13-using-the-flush-directive-with-a-list.md)

[A.14 使用 flush 指示詞沒有清單搭配](../../parallel/openmp/a-14-using-the-flush-directive-without-a-list.md)

[A.15 判斷使用的執行緒數目](../../parallel/openmp/a-15-determining-the-number-of-threads-used.md)

[A.16 使用鎖定](../../parallel/openmp/a-16-using-locks.md)

[A.17 使用可巢狀鎖定](../../parallel/openmp/a-17-using-nestable-locks.md)

[A.18 巢狀指示詞使用](../../parallel/openmp/a-18-nested-for-directives.md)

[A.19 巢狀使用工作共用指示詞的範例](../../parallel/openmp/a-19-examples-showing-incorrect-nesting-of-work-sharing-directives.md)

[A.20 繫結 barrier 指示詞](../../parallel/openmp/a-20-binding-of-barrier-directives.md)

[A.21 使用 private 子句設定變數](../../parallel/openmp/a-21-scoping-variables-with-the-private-clause.md)

[A.22 使用 default （none） 子句](../../parallel/openmp/a-22-using-the-default-none-clause.md)

[A.23 ordered 指示詞範例](../../parallel/openmp/a-23-examples-of-the-ordered-directive.md)

[A.24 private 子句範例](../../parallel/openmp/a-24-example-of-the-private-clause.md)

[A.25 copyprivate 資料屬性子句範例](../../parallel/openmp/a-25-examples-of-the-copyprivate-data-attribute-clause.md)

[A.26 使用 threadprivate 指示詞](../../parallel/openmp/a-26-using-the-threadprivate-directive.md)

[A.27 使用 C99 可變長度陣列](../../parallel/openmp/a-27-use-of-c99-variable-length-arrays.md)

[A.28 使用 num_threads 子句](../../parallel/openmp/a-28-use-of-num-threads-clause.md)

[使用工作共用 A.29 在 critical 建構](../../parallel/openmp/a-29-use-of-work-sharing-constructs-inside-a-critical-construct.md)

[A.30 使用 Reprivatization](../../parallel/openmp/a-30-use-of-reprivatization.md)

[A.31 安全執行緒鎖定函式](../../parallel/openmp/a-31-thread-safe-lock-functions.md)

[B.執行階段程式庫函式的虛設常式](../../parallel/openmp/b-stubs-for-run-time-library-functions.md)

[C.OpenMP C 和 C++ 文法](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)

[C.1 標記法](../../parallel/openmp/c-1-notation.md)

[C.2 規則](../../parallel/openmp/c-2-rules.md)

[D.使用 schedule 子句](../../parallel/openmp/d-using-the-schedule-clause.md)

[E.OpenMP C/C++ 中的實作定義行為](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)

[F.2.0 版中的新功能和釐清的內容](../../parallel/openmp/f-new-features-and-clarifications-in-version-2-0.md)

## <a name="see-also"></a>另請參閱

[C 和 c + + 應用程式開發介面](../../parallel/openmp/openmp-c-and-cpp-application-program-interface.md)