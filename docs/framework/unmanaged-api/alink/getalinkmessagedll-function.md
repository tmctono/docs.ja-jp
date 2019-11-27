---
title: GetALinkMessageDll 関数
ms.date: 03/30/2017
api_name:
- GetALinkMessageDll
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- GetALinkMessageDll
helpviewer_keywords:
- Alink API, GetALinkMessageDll function
- GetALinkMessageDll function
ms.assetid: 67985a22-88a2-4c54-8d99-4bcde9d6213e
topic_type:
- apiref
ms.openlocfilehash: 63719d0c6e13768e9dc7ed80e52e2a293e32a8a1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449348"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="dff18-102">GetALinkMessageDll 関数</span><span class="sxs-lookup"><span data-stu-id="dff18-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="dff18-103">メッセージ DLL を検索して読み込みます。</span><span class="sxs-lookup"><span data-stu-id="dff18-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="dff18-104">メッセージ DLL が見つからないか、または読み込むことができなかった場合は0を返します。</span><span class="sxs-lookup"><span data-stu-id="dff18-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="dff18-105">メッセージ DLL は、名前が言語 ID または現在のディレクトリ内のサブディレクトリにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="dff18-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff18-106">構文</span><span class="sxs-lookup"><span data-stu-id="dff18-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="dff18-107">要件</span><span class="sxs-lookup"><span data-stu-id="dff18-107">Requirements</span></span>  
 <span data-ttu-id="dff18-108">**ヘッダー:** alink</span><span class="sxs-lookup"><span data-stu-id="dff18-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="dff18-109">**ライブラリ**: alink</span><span class="sxs-lookup"><span data-stu-id="dff18-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff18-110">参照</span><span class="sxs-lookup"><span data-stu-id="dff18-110">See also</span></span>

- [<span data-ttu-id="dff18-111">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="dff18-111">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
