# Feladatok — CUSTOMER/ORDER_HDR/ORDER_ITEM

> **Tanulási példa – ne másold be ZH-megoldásként.** A mintákban `<helyőrző>` van; töltsd ki a feladat szerint.

Összesen ebben a fájlban: **20** feladat.

## F061 · LEVEL 0
Listázd a CUSTOMER neveket.

## F062 · LEVEL 0
ORDER_HDR sorok egy dátumtól.

## F063 · LEVEL 1
JOIN customer–order_hdr.

## F064 · LEVEL 1
JOIN order_hdr–order_item.

## F065 · LEVEL 2
GROUP BY: vevőnkénti rendelésszám.

## F066 · LEVEL 2
HAVING: vevők >= 2 rendeléssel.

## F067 · LEVEL 2
LEFT: vevők rendelés nélkül.

## F068 · LEVEL 3
Subquery: átlagos tételár feletti tételek.

## F069 · LEVEL 3
INSERT ALL: 5 order_item.

## F070 · LEVEL 3
MERGE: tétel mennyiség frissítés.

## F071 · LEVEL 4
VIEW: rendelés + SUM(qty) + LISTAGG(product_name).

## F072 · LEVEL 4
Top-1 legnagyobb összegű rendelés (ROWNUM).

## F073 · LEVEL 1
UPDATE order státusz.

## F074 · LEVEL 1
DELETE cancelled order items.

## F075 · LEVEL 2
CASE order status szövegre.

## F076 · LEVEL 3
CTAS üres order_item_copy.

## F077 · LEVEL 0
COUNT order_hdr.

## F078 · LEVEL 4
INSERT FIRST szétválogatás order_date szerint két hist táblába.

## F079 · LEVEL 2
JOIN lánc customer–hdr–item.

## F080 · LEVEL 3
EXISTS: customers who ordered product `<sku>`.
