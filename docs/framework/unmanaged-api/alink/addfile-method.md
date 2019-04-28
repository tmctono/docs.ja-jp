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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 056d1ac0ffd3ad7fa7cb1f86ae13331ac38b3eff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775649"
---
# <a name="addfile-method"></a><span data-ttu-id="e0bbf-102">AddFile メソッド</span><span class="sxs-lookup"><span data-stu-id="e0bbf-102">AddFile Method</span></span>
<span data-ttu-id="e0bbf-103">アセンブリには、ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-103">Adds files to the assembly.</span></span> <span data-ttu-id="e0bbf-104">非バインド モジュールの作成にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0bbf-105">構文</span><span class="sxs-lookup"><span data-stu-id="e0bbf-105">Syntax</span></span>  
  
```  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0bbf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0bbf-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e0bbf-107">追加する対象のアセンブリの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="e0bbf-108">追加するファイルの完全修飾名。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0bbf-109">COM + FileDef フラグなど`ffContainsNoMetaData`と`ffWriteable`します。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="e0bbf-110">`dwFlags` 渡される[DefineFile メソッド](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)します。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e0bbf-111">[IMetaDataEmit インターフェイス](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)メタデータを出力するために必要な場合に使用するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="e0bbf-112">追加されたファイルの一意の ID を格納する場所へのポインター。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0bbf-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="e0bbf-113">Return Value</span></span>  
 <span data-ttu-id="e0bbf-114">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0bbf-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="e0bbf-115">Requirements</span></span>  
 <span data-ttu-id="e0bbf-116">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0bbf-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0bbf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0bbf-117">See also</span></span>

- [<span data-ttu-id="e0bbf-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0bbf-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="e0bbf-119">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="e0bbf-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="e0bbf-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="e0bbf-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
