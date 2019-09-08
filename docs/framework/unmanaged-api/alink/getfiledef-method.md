---
title: GetFileDef メソッド
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5db205993bc1a0665dc0003948ce805813251f48
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787453"
---
# <a name="getfiledef-method"></a><span data-ttu-id="c1ad3-102">GetFileDef メソッド</span><span class="sxs-lookup"><span data-stu-id="c1ad3-102">GetFileDef Method</span></span>
<span data-ttu-id="c1ad3-103">ALink によって割り当てられたトークンとは対照的に、メタデータで使用される実際の FileDef トークンを取得します。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ad3-104">構文</span><span class="sxs-lookup"><span data-stu-id="c1ad3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1ad3-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c1ad3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c1ad3-106">アセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="c1ad3-107">AddFile メソッドまたは AddImport メソッドから取得された追加ファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="c1ad3-108">FileDef トークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1ad3-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c1ad3-109">Return Value</span></span>  
 <span data-ttu-id="c1ad3-110">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1ad3-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="c1ad3-111">Requirements</span></span>  
 <span data-ttu-id="c1ad3-112">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1ad3-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ad3-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1ad3-113">See also</span></span>

- [<span data-ttu-id="c1ad3-114">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1ad3-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c1ad3-115">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c1ad3-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c1ad3-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="c1ad3-116">ALink API</span></span>](index.md)
