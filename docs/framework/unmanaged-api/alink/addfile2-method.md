---
title: AddFile2 メソッド
ms.date: 03/30/2017
api_name:
- AddFile2
- IALink2.AddFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile2
helpviewer_keywords:
- AddFile2 method
ms.assetid: 03bc49bf-a89b-4fb6-a88d-97482e061195
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c3a6892dbed172c0be3b036014d393657dbc8593
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777521"
---
# <a name="addfile2-method"></a><span data-ttu-id="07678-102">AddFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="07678-102">AddFile2 Method</span></span>
<span data-ttu-id="07678-103">アセンブリにファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="07678-103">Adds files to the assembly.</span></span> <span data-ttu-id="07678-104">は、バインドされていないモジュールを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="07678-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07678-105">構文</span><span class="sxs-lookup"><span data-stu-id="07678-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="07678-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="07678-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="07678-107">ファイルが追加されるアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="07678-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="07678-108">追加するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="07678-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="07678-109">Com `FileDef` + フラグ ( `ffContainsNoMetaData`や`ffWriteable`など)。</span><span class="sxs-lookup"><span data-stu-id="07678-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="07678-110">`dwFlags`は、[メソッド](../metadata/imetadataassemblyemit-definefile-method.md)に渡されます。</span><span class="sxs-lookup"><span data-stu-id="07678-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="07678-111">[IMetaDataEmit2 インターフェイス](../metadata/imetadataemit2-interface.md)インターフェイスへのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="07678-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="07678-112">追加するファイルの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="07678-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07678-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="07678-113">Return Value</span></span>  
 <span data-ttu-id="07678-114">メソッドが成功した場合、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="07678-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07678-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="07678-115">Requirements</span></span>  
 <span data-ttu-id="07678-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="07678-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07678-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="07678-117">See also</span></span>

- [<span data-ttu-id="07678-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07678-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="07678-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="07678-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="07678-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="07678-120">ALink API</span></span>](index.md)
