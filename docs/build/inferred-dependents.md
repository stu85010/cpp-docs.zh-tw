---
title: 推斷相依
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 958a33c29be0d68fee1044fff1d81235ea9370c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641372"
---
# <a name="inferred-dependents"></a>推斷相依

推斷的相依衍生自推斷規則，而且明確的相依項目之前評估。 如果推斷的相依為相對於其目標過期時，NMAKE 就會叫用命令區塊，相依性。 如果推斷的相依不存在，或對自身的相依性而言已過期，NMAKE 首先會更新推斷的相依。 如需推斷的相依性的詳細資訊，請參閱[推斷規則](../build/inference-rules.md)。

## <a name="see-also"></a>另請參閱

[相依性](../build/dependents.md)