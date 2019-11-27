---
title: AddFile メソッド
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446687"
---
# <a name="addfile-method"></a><span data-ttu-id="5ef48-102">AddFile メソッド</span><span class="sxs-lookup"><span data-stu-id="5ef48-102">AddFile Method</span></span>
<span data-ttu-id="5ef48-103">アセンブリにファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="5ef48-103">Adds files to the assembly.</span></span> <span data-ttu-id="5ef48-104">は、バインドされていないモジュールを作成するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5ef48-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef48-105">構文</span><span class="sxs-lookup"><span data-stu-id="5ef48-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ef48-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ef48-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="5ef48-107">補強するアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="5ef48-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="5ef48-108">追加するファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="5ef48-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5ef48-109">`ffContainsNoMetaData` や `ffWriteable`などの COM + FileDef フラグ。</span><span class="sxs-lookup"><span data-stu-id="5ef48-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="5ef48-110">`dwFlags` は、の[メソッド](../metadata/imetadataassemblyemit-definefile-method.md)に渡されます。</span><span class="sxs-lookup"><span data-stu-id="5ef48-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="5ef48-111">必要に応じて、メタデータを出力するために使用される[IMetaDataEmit インターフェイス](../metadata/imetadataemit-interface.md)インターフェイス。</span><span class="sxs-lookup"><span data-stu-id="5ef48-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="5ef48-112">追加されたファイルの一意の ID が格納される場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="5ef48-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ef48-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="5ef48-113">Return Value</span></span>  
 <span data-ttu-id="5ef48-114">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="5ef48-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef48-115">要件</span><span class="sxs-lookup"><span data-stu-id="5ef48-115">Requirements</span></span>  
 <span data-ttu-id="5ef48-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ef48-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef48-117">参照</span><span class="sxs-lookup"><span data-stu-id="5ef48-117">See also</span></span>

- [<span data-ttu-id="5ef48-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ef48-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="5ef48-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5ef48-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="5ef48-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="5ef48-120">ALink API</span></span>](index.md)
