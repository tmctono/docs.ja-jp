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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 41e79a4c9587e3e738039cbf6a84087a2e7fc9b1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741959"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="059e8-102">GetALinkMessageDll 関数</span><span class="sxs-lookup"><span data-stu-id="059e8-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="059e8-103">検索し、メッセージ DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="059e8-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="059e8-104">メッセージ DLL が発見または読み込まれた場合は、0 を返します。</span><span class="sxs-lookup"><span data-stu-id="059e8-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="059e8-105">メッセージ DLL は、言語 ID の名前を持つサブディレクトリまたは現在のディレクトリ内のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="059e8-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="059e8-106">構文</span><span class="sxs-lookup"><span data-stu-id="059e8-106">Syntax</span></span>  
  
```cpp  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="059e8-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="059e8-107">Requirements</span></span>  
 <span data-ttu-id="059e8-108">**ヘッダー:** alink.h</span><span class="sxs-lookup"><span data-stu-id="059e8-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="059e8-109">**ライブラリ**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="059e8-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="059e8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="059e8-110">See also</span></span>

- [<span data-ttu-id="059e8-111">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="059e8-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
