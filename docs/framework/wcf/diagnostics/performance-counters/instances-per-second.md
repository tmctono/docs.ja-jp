---
title: 1 秒あたりのインスタンス
ms.date: 03/30/2017
ms.assetid: 74579397-1058-4278-80cf-2d00854a480f
ms.openlocfilehash: 9b78707f3815fd370d3398f1a7b422ee4bf2d369
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541227"
---
# <a name="instances-per-second"></a>1 秒あたりのインスタンス
カウンター名 : 1 秒あたりに作成されたインスタンス。  
  
## <a name="description"></a>説明  
 1 秒あたりに作成されたサービス インスタンスの合計数です。  
  
 このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
