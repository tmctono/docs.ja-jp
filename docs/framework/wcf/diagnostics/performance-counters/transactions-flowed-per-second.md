---
title: 1 秒あたりのトランザクション フロー
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: d55856a5d820df2c668863a2a3e853995a113143
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552207"
---
# <a name="transactions-flowed-per-second"></a>1 秒あたりのトランザクション フロー
カウンター名 : 1 秒あたりのトランザクション フロー  
  
## <a name="description"></a>説明  
 この操作に対して実行された 1 秒あたりのトランザクションの数です。 このカウンターは、操作に送信されたメッセージにトランザクション ID が存在する場合にインクリメントされます。  
  
 このカウンターは、次の式を使用して計算された値を持つ、パフォーマンスカウンターの種類 [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))です。  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
