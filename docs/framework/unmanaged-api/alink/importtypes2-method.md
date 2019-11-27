---
title: ImportTypes2 メソッド
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 8dae903ab76ab83ac0818c4bc4a76e81094bdf65
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445669"
---
# <a name="importtypes2-method"></a><span data-ttu-id="1f8f9-102">ImportTypes2 メソッド</span><span class="sxs-lookup"><span data-stu-id="1f8f9-102">ImportTypes2 Method</span></span>
<span data-ttu-id="1f8f9-103">型のインポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-103">Initiates the import of types.</span></span> <span data-ttu-id="1f8f9-104">[Importfile メソッド](importfile-method.md)を使用してインポートされた各スコープから型のインポートを開始するには、このメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f8f9-105">構文</span><span class="sxs-lookup"><span data-stu-id="1f8f9-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f8f9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f8f9-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1f8f9-107">インポート先のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1f8f9-108">インポート元のファイルの ID。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="1f8f9-109">インポート元の0から始まるスコープ。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="1f8f9-110">指定されたスコープ内の型の列挙子ハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="1f8f9-111">必要に応じて、 [IMetaDataImport2 インターフェイス](../metadata/imetadataimport2-interface.md)インターフェイスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="1f8f9-112">必要に応じて、指定されたスコープ内の型の数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f8f9-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="1f8f9-113">Return Value</span></span>  
 <span data-ttu-id="1f8f9-114">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f8f9-115">要件</span><span class="sxs-lookup"><span data-stu-id="1f8f9-115">Requirements</span></span>  
 <span data-ttu-id="1f8f9-116">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="1f8f9-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f8f9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="1f8f9-117">See also</span></span>

- [<span data-ttu-id="1f8f9-118">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f8f9-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="1f8f9-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="1f8f9-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="1f8f9-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="1f8f9-120">ALink API</span></span>](index.md)
