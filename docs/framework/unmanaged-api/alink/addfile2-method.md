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
ms.openlocfilehash: 8dadf9ec8f896b03e4918b21f5153c1b747010fd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446666"
---
# <a name="addfile2-method"></a><span data-ttu-id="59b1f-102">AddFile2 メソッド</span><span class="sxs-lookup"><span data-stu-id="59b1f-102">AddFile2 Method</span></span>
<span data-ttu-id="59b1f-103">アセンブリにファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="59b1f-103">Adds files to the assembly.</span></span> <span data-ttu-id="59b1f-104">は、バインドされていないモジュールを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="59b1f-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b1f-105">構文</span><span class="sxs-lookup"><span data-stu-id="59b1f-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile2(  
    mdAssembly AssemblyID,  
    LPCWSTR pszFilename,  
    DWORD dwFlags,  
    IMetaDataEmit2* pEmitter,  
    mdFile* pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="59b1f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="59b1f-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="59b1f-107">ファイルが追加されるアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="59b1f-107">ID for the assembly to which the file is added.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="59b1f-108">追加するファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="59b1f-108">Name of the file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="59b1f-109">COM + は、`ffContainsNoMetaData` や `ffWriteable`などの `FileDef` フラグを持ちます。</span><span class="sxs-lookup"><span data-stu-id="59b1f-109">COM+ `FileDef` flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="59b1f-110">`dwFlags` は、の[メソッド](../metadata/imetadataassemblyemit-definefile-method.md)に渡されます。</span><span class="sxs-lookup"><span data-stu-id="59b1f-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="59b1f-111">[IMetaDataEmit2 インターフェイス](../metadata/imetadataemit2-interface.md)インターフェイスへのインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="59b1f-111">Interface to [IMetaDataEmit2 Interface](../metadata/imetadataemit2-interface.md) interface.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="59b1f-112">追加するファイルの ID を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="59b1f-112">Receives ID for the file being added.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59b1f-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="59b1f-113">Return Value</span></span>  
 <span data-ttu-id="59b1f-114">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="59b1f-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b1f-115">要件</span><span class="sxs-lookup"><span data-stu-id="59b1f-115">Requirements</span></span>  
 <span data-ttu-id="59b1f-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="59b1f-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b1f-117">参照</span><span class="sxs-lookup"><span data-stu-id="59b1f-117">See also</span></span>

- [<span data-ttu-id="59b1f-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59b1f-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="59b1f-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="59b1f-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="59b1f-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="59b1f-120">ALink API</span></span>](index.md)
