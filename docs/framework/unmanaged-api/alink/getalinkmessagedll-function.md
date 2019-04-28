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
ms.openlocfilehash: edd83e62b08aa7892c01577cd8c46f9d965c0894
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789897"
---
# <a name="getalinkmessagedll-function"></a><span data-ttu-id="a1142-102">GetALinkMessageDll 関数</span><span class="sxs-lookup"><span data-stu-id="a1142-102">GetALinkMessageDll Function</span></span>
<span data-ttu-id="a1142-103">検索し、メッセージ DLL を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a1142-103">Finds and loads the message DLL.</span></span> <span data-ttu-id="a1142-104">メッセージ DLL が発見または読み込まれた場合は、0 を返します。</span><span class="sxs-lookup"><span data-stu-id="a1142-104">Returns 0 if the message DLL could not be located or loaded.</span></span> <span data-ttu-id="a1142-105">メッセージ DLL は、言語 ID の名前を持つサブディレクトリまたは現在のディレクトリ内のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="a1142-105">The message DLL should be either in a subdirectory whose name is a language ID, or in the current directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1142-106">構文</span><span class="sxs-lookup"><span data-stu-id="a1142-106">Syntax</span></span>  
  
```  
HINSTANCE WINAPI GetALinkMessageDll();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a1142-107">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1142-107">Requirements</span></span>  
 <span data-ttu-id="a1142-108">**ヘッダー:** alink.h</span><span class="sxs-lookup"><span data-stu-id="a1142-108">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="a1142-109">**ライブラリ**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="a1142-109">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1142-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1142-110">See also</span></span>

- [<span data-ttu-id="a1142-111">Al.exe (アセンブリ リンカー)</span><span class="sxs-lookup"><span data-stu-id="a1142-111">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
