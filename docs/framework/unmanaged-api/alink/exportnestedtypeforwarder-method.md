---
title: ExportNestedTypeForwarder メソッド
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438417"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="2c154-102">ExportNestedTypeForwarder メソッド</span><span class="sxs-lookup"><span data-stu-id="2c154-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="2c154-103">入れ子になった型の型フォワーダーを、指定されたアセンブリの型テーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="2c154-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c154-104">構文</span><span class="sxs-lookup"><span data-stu-id="2c154-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c154-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c154-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2c154-106">エクスポート元のアセンブリの ID。</span><span class="sxs-lookup"><span data-stu-id="2c154-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2c154-107">型を定義するファイルのファイルトークンまたはアセンブリ ID。</span><span class="sxs-lookup"><span data-stu-id="2c154-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="2c154-108">型のトークン。</span><span class="sxs-lookup"><span data-stu-id="2c154-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="2c154-109">親の種類のトークン。</span><span class="sxs-lookup"><span data-stu-id="2c154-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="2c154-110">エクスポートする完全修飾型名。</span><span class="sxs-lookup"><span data-stu-id="2c154-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2c154-111">`tdPublic` や `tdNested`などのフラグを `ComType` します。</span><span class="sxs-lookup"><span data-stu-id="2c154-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="2c154-112">エクスポートの種類のトークンを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="2c154-112">Receives token of export type.</span></span> <span data-ttu-id="2c154-113">これは、入れ子にされた型を出力する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="2c154-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c154-114">戻り値</span><span class="sxs-lookup"><span data-stu-id="2c154-114">Return Value</span></span>  
 <span data-ttu-id="2c154-115">メソッドが成功した場合は S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="2c154-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c154-116">要件</span><span class="sxs-lookup"><span data-stu-id="2c154-116">Requirements</span></span>  
 <span data-ttu-id="2c154-117">Alink. h が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c154-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c154-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c154-118">See also</span></span>

- [<span data-ttu-id="2c154-119">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c154-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2c154-120">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="2c154-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2c154-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="2c154-121">ALink API</span></span>](index.md)
