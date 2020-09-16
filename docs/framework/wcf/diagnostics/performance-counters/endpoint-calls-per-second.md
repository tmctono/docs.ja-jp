---
title: 'エンドポイント : 1 秒あたりの呼び出し回数'
ms.date: 03/30/2017
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
ms.openlocfilehash: 7a3a9bcdb3485efa01ceed61495dd87d64424d50
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550320"
---
# <a name="endpoint-calls-per-second"></a>エンドポイント : 1 秒あたりの呼び出し回数
カウンター名 : 1 秒あたりの呼び出し  
  
## <a name="description"></a>説明  
 このエンドポイントが 1 秒あたりに呼び出される回数です。  
  
 このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
